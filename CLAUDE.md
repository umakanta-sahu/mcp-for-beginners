# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is **MCP for Beginners**, a Microsoft open-source educational curriculum that teaches the Model Context Protocol (MCP) through Markdown lessons and runnable code samples in **five languages: C#, Java, Python, TypeScript, and JavaScript**. It is a *learning repository*, not a single deployable application. There is no top-level build, no monorepo package manager, and no shared test suite. Each lesson and each language sample is an independent, self-contained project.

The authoritative entry points are `README.md` (curriculum map) and `study_guide.md` (visual map + recommended learning paths).

## Repository structure

Lessons are numbered top-level directories (`00-Introduction` … `10-Streamlining...`). Each lesson is a `README.md` plus, where relevant, a `samples/` and/or `solution/` folder:

- **`00`–`02`** — Conceptual lessons (Introduction, Core Concepts, Security). Mostly prose, no code to build.
- **`03-GettingStarted`** — The core hands-on track. Subfolders `01-first-server` through `09-deployment`, each with per-language `solution/` directories. `03-GettingStarted/samples/{csharp,java,javascript,python,typescript}` holds the canonical "calculator" MCP server in every language.
- **`04-PracticalImplementation`** — Advanced calculator samples per language; the C# version (`samples/csharp`) is a **.NET Aspire** multi-project solution (`AppHost`, `Calculator`, `ServiceDefaults`).
- **`05-AdvancedTopics`** — One subfolder per topic (OAuth2, routing, sampling, scaling, multi-modality, realtime streaming/search, etc.). Mixed Python and Java. Shared Python deps in `05-AdvancedTopics/requirements.txt`.
- **`06`–`09`** — Community contributions, early-adoption lessons, best practices, and case studies (`09-CaseStudy/docs-mcp` has a runnable Python solution).
- **`10-Streamlining...`** — A four-part hands-on lab (`lab1`–`lab4`) building an MCP server with the AI Toolkit; Python projects use `pyproject.toml` + `uv`.

### Directories you should generally NOT touch

- **`translations/`** — 40+ language subfolders, each a full mirror of the curriculum. **Auto-generated** by the Co-op Translator GitHub Action. Never hand-edit; edit the English source instead.
- **`translated_images/`** — Auto-generated localized images (very large directory).
- **`images/`** — Source English images, referenced by lessons.

## How code samples are organized

The same conceptual sample (e.g. the calculator MCP server) is reimplemented per language. There is no shared code between language versions — treat each `samples/<language>/` or `solution/<language>/` folder as its own project rooted at its manifest file:

| Language   | Manifest / project file                | Typical layout |
|------------|----------------------------------------|----------------|
| Python     | `*.py` (single file), `requirements.txt`, or `pyproject.toml` | FastMCP-based servers; `uv` for newer labs |
| TypeScript | `package.json` + `tsconfig.json`       | source in `src/`, builds to `build/` |
| JavaScript | `package.json`                         | single `index.js` entry, run directly with node |
| C#         | `*.csproj` / `*.sln`                    | `src/` with `Program.cs`; some use .NET Aspire |
| Java       | `pom.xml` + Maven wrapper (`mvnw`)     | Spring Boot, package `com.microsoft.mcp.sample` |

## Common commands

Always `cd` into the specific sample directory (the one containing the manifest) before running these.

**Python** (single-file samples, e.g. `03-GettingStarted/samples/python`):
```bash
pip install mcp                 # or: pip install -r requirements.txt
python mcp_calculator_server.py
```

**Python** (uv-based labs, e.g. `10-Streamlining.../lab3/code/weather_mcp`):
```bash
uv venv
uv pip install -r pyproject.toml --extra dev
uv run <entry>                  # e.g. uv run fastapi dev main.py
```

**TypeScript** (e.g. `03-GettingStarted/samples/typescript`):
```bash
npm install
npm run build                   # tsc, then runs build/index.js
```

**JavaScript** (e.g. `03-GettingStarted/samples/javascript`):
```bash
npm install
npm start                       # node index.js
```

**C#** (e.g. `03-GettingStarted/samples/csharp/src`):
```bash
dotnet run --project calculator.csproj
```

**Java** (e.g. `03-GettingStarted/samples/java/calculator`):
```bash
./mvnw spring-boot:run          # Maven wrapper; use mvnw.cmd on Windows
./mvnw clean package            # build a jar
```

There is **no repository-wide build, lint, or test command.** Each sample's own `README.md` is the source of truth for that sample's exact build/run/test steps — read it before running, as conventions vary (stdio vs SSE vs HTTP-streaming transport, Docker, Azure deployment, etc.).

### Running/testing MCP servers

Most servers default to the **stdio** transport and are exercised by an MCP client rather than run standalone. The standard local workflow is to register the server in a `.vscode/mcp.json` file and drive it from GitHub Copilot Chat (agent mode) in VS Code, or to use the **MCP Inspector** (`npm run inspect` / `npm run inspector` where defined). Lesson `03-GettingStarted/08-testing` covers testing approaches; some lessons add SSE (`05-sse-server`) or HTTP streaming (`06-http-streaming`) transports with separate client/server projects.

## Conventions when editing this repository

- **English is the source.** Make all content changes to the English Markdown/code under the numbered lesson directories. The `translations/` and `translated_images/` trees are regenerated automatically by the Co-op Translator Action on push to `main` — do not edit them.
- **Keep cross-references consistent.** Lessons link heavily to each other and to per-language `solution/` folders using relative paths. When renaming or moving files, update the referring `README.md` links.
- **Match the existing per-language sample when adding a new one.** New samples should mirror the structure, naming, and transport approach of the equivalent sample in the other languages so the curriculum stays parallel.
- **Educational clarity over cleverness.** Code is meant to be read by beginners; favor explicit, well-commented implementations consistent with the surrounding sample.
- **Pin SDK/dependency versions** the way existing samples do (e.g. `@modelcontextprotocol/sdk` in `package.json`, `mcp==1.9.3` in `pyproject.toml`), since lessons reference specific behaviors.

## Contribution notes

This is a Microsoft project requiring a Contributor License Agreement (CLA) on pull requests; a CLA bot handles this automatically. The repo follows the Microsoft Open Source Code of Conduct. Content is MIT-licensed.

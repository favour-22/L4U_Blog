Skip to content
Chat history

You said:
How tcan i build a finacen traking application  where AI will be involved gemini API .Using superbase
ChatGPT said:

Thought for 7s
Nice — that’s a great project idea. Below I’ll give you a complete, practical plan and starter code to build a finance-tracking app using Supabase for your backend (DB + Auth + realtime) and Google’s Gemini API for the AI parts (transaction categorization, NLP queries, insights, summaries, forecasting helpers, embeddings for search). I’ll include architecture, DB schema, concrete implementation patterns (where to call Gemini, how to keep keys safe), example code for common flows, and ideas to evolve the MVP into a production app.

I checked the current docs for Gemini and Supabase while preparing this so the integration details match the official APIs. 
Supabase
+4
Google AI for Developers
+4
Google AI for Developers
+4

1) High-level architecture (recommended)
Frontend (Next.js or React)

UI for adding/connecting accounts, viewing transactions, budgets, charts, chat/insight interface.

supabase.com
supabase.com
. For example, we can ask the AI: “List all columns in the users table” or “Generate a SQL query to fetch posts by a given user,” and it will use the live schema. If we use REST/GraphQL APIs, we will provide the OpenAPI spec or GraphQL schema to the AI so it can generate client functions or SQL queries accurately. In short, by feeding the AI our file structure or database schema, we enable it to produce contextually correct code (e.g. creating database migrations for new features).
. This means as we type or describe tasks (e.g., “build a Next.js page”), the IDE can suggest or fill in code snippets.
CodeRabbit for Reviews: We will use CodeRabbit for our pull request reviews. CodeRabbit provides automated, line-by-line AI reviews of our code and suggests fixes
coderabbit.ai
. It can also generate summaries of changes or release notes from a commit diff
coderabbit.ai
. In practice, after creating a feature branch and pushing a PR, CodeRabbit will analyze the diff, point out issues (like missing error checks or inconsistent styles), and even propose code corrections. It will also produce a concise PR description or commit message summarizing what changed. This tool ensures faster, AI-assisted review cycles and higher code quality.
Version Control & Collaboration: We’ll use Git/GitHub for collaboration. CodeRabbit will be connected to our GitHub repo, so every PR triggers an AI review. We’ll follow good commit practices, and can even prompt AI to suggest commit messages by describing our changes (e.g., using the diff as context in Gemini or CodeRabbit’s chat).
We will craft clear prompts for the AI tools. For example:
Feature Generation:
“Write a Jest test suite for the loginUser function, covering successful login (valid credentials), incorrect password, and missing fields errors. Mock Supabase Auth calls.”
These prompts guide the AI to produce concrete code or tests. By including specifics (function names, fields, frameworks) we ensure the AI output is relevant. In practice, we might also prepend use context7 for heavy-lifting code prompts to pull in up-to-date examples
github.com
, or use Gemini CLI with our project context for database/API tasks. Sample Prompt 1: “Generate a Jest test suite for the user authentication function (loginUser). Include tests for valid login, invalid password, and empty credentials.”
Sample Prompt 2: “Create a Next.js API route handler for /api/createPost that accepts title and content, validates them, and inserts a new row into the Supabase posts table.” These example prompts show how we turn feature requirements into AI-driven tasks.


Sources


No file chosenNo file chosen
ChatGPT can make mistakes. Check important info.

github.com
trae.ai
. For database and API interactions, we’ll connect our Supabase project via the Model Context Protocol (MCP). MCP allows tools like the Gemini CLI to query our Supabase database schema and execute commands based on it
supabase.com
supabase.com
trae.ai
. This means as we type or describe tasks (e.g., “build a Next.js page”), the IDE can suggest or fill in code snippets.
CodeRabbit for Reviews: We will use CodeRabbit for our pull request reviews. CodeRabbit provides automated, line-by-line AI reviews of our code and suggests fixes
coderabbit.ai
. It can also generate summaries of changes or release notes from a commit diff
coderabbit.ai
. In practice, after creating a feature branch and pushing a PR, CodeRabbit will analyze the diff, point out issues (like missing error checks or inconsistent styles), and even propose code corrections. It will also produce a concise PR description or commit message summarizing what changed. This tool ensures faster, AI-assisted review cycles and higher code quality.
Prompting Strategy
We will craft clear prompts for the AI tools. For example:
Testing:
“Write a Jest test suite for the loginUser function, covering successful login (valid credentials), incorrect password, and missing fields errors. Mock Supabase Auth calls.”
These prompts guide the AI to produce concrete code or tests. By including specifics (function names, fields, frameworks) we ensure the AI output is relevant. In practice, we might also prepend use context7 for heavy-lifting code prompts to pull in up-to-date examples
github.com
, or use Gemini CLI with our project context for database/API tasks. Sample Prompt 1: “Generate a Jest test suite for the user authentication function (loginUser). Include tests for valid login, invalid password, and empty credentials.”
GitHub - cursor/cursor: The AI Code Editor

https://github.com/cursor/cursor


https://www.trae.ai/

Gemini CLI MCP Tutorial: Setup, Commands, & Practical Use (Step by Step Example) | by Joe Njenga | Jun, 2025 | Medium

https://github.blog/ai-and-ml/github-copilot/how-to-generate-unit-tests-with-github-copilot-tips-and-examples/

# L4U_Blog

## Project Title & Description

**L4U_Blog** is a multi-user blogging application where developers and community members can create, share, and discover articles. It features:

- User authentication (Supabase Auth)
- Markdown blog post creation and rendering
- Image uploads (including AI-generated images)
- Dark and light mode toggle
- Social sharing of blog posts
- AI-powered features (summaries, SEO, tags, image generation via Gemini)

This project matters because it provides a platform for knowledge sharing, personal portfolios, and demonstrates modern web and AI-assisted development practices.

---

## 🛠️ Tech Stack

### Languages
- **TypeScript** (preferred) / JavaScript

### Frontend
- **Next.js** (React-based, server-side rendering, routing)
- **Tailwind CSS** (styling, dark/light mode)
- **shadcn/ui** (prebuilt styled components)
- **react-markdown** (Markdown rendering)
- **remark-gfm** (GitHub-flavored Markdown)
- **Next.js Image** (image optimization)

### Backend & Database
- **Supabase** (PostgreSQL, Auth, Storage)
- **Supabase Edge Functions** or Next.js API Routes (for server logic)

### AI & Tooling
- **Gemini CLI** (Google Generative AI for text/image)
- **Cursor** and **Træ (TRAE)** (AI-powered code editors)
- **CodeRabbit** (AI code review in PRs)

### Testing
- **Jest** & **React Testing Library** (unit/integration tests)

### Deployment
- **GitHub** (repo: [favour-22/L4U_Blog](https://github.com/favour-22/L4U_Blog))
- **Vercel** or Supabase Hosting

---

## 🧠 AI Integration Strategy

### Code & Feature Generation
- Use AI editors (Cursor, Træ) to scaffold features from natural-language prompts (e.g., "Create a Markdown editor page").
- Use Gemini CLI for database models, API routes, and code generation (e.g., "create Supabase model for posts").
- Use Context7 in prompts to ensure up-to-date code and docs.

### Testing Support
- Prompt AI to generate Jest/RTL tests for functions and components (e.g., "Write tests for user registration").
- Use AI to cover both success and error scenarios.

### Documentation & Comments
- Use AI to generate docstrings, inline comments, and keep README up-to-date (e.g., "Summarize this module").
- Feed code context or API schemas to AI for accurate explanations.

### Context-Aware & API-Aware Generation
- Use Context7 and MCP to ground AI in project specifics (file tree, DB schema, OpenAPI spec).
- Use Gemini CLI to query Supabase schema and generate code based on live DB/API.

---

## 🔒 Plan for In-Editor & PR Review Tooling

- **Cursor/Træ**: AI code completion and feature scaffolding in the editor.
- **CodeRabbit**: Automated, line-by-line AI reviews for every PR (suggests fixes, generates summaries, and commit messages).
- **GitHub**: Version control and collaboration; CodeRabbit is connected for PR reviews.

---

## 📝 Prompting Strategy

**Feature Generation Example:**
> Generate a Next.js API route `/api/posts/create` that handles creating a new blog post. It should validate the input fields (title and content) and save the post to Supabase, returning an error if validation fails.

**Testing Example:**
> Write a Jest test suite for the `loginUser` function, covering successful login (valid credentials), incorrect password, and missing fields errors. Mock Supabase Auth calls.

**Context-Aware Example:**
> (With Context7) Generate a SQL query to fetch all published posts by a given user from the Supabase schema.

---

## 📋 Tasks & Capstone Planning

### 0. Capstone Planning (Mandatory)

**Deliverable:**
- Public GitHub repository: [favour-22/L4U_Blog](https://github.com/favour-22/L4U_Blog)
- This `README.md` with detailed project plan:
  - Project Title & Description
  - Tech Stack
  - AI Integration Strategy
  - In-Editor/PR Review Tooling
  - Prompting Strategy

---

## 📚 References & Citations

- [Cursor: The AI Code Editor](https://github.com/cursor/cursor)
- [TRAE: Collaborate with Intelligence](https://www.trae.ai/)
- [Gemini CLI MCP Tutorial](https://medium.com/@joe.njenga/gemini-cli-mcp-tutorial-setup-commands-practical-use-step-by-step-example-b57f55db5f4a)
- [Context7 MCP Server](https://github.com/upstash/context7)
- [How to generate unit tests with GitHub Copilot](https://github.blog/ai-and-ml/github-copilot/how-to-generate-unit-tests-with-github-copilot-tips-and-examples/)
- [Supabase MCP Docs](https://supabase.com/docs/guides/getting-started/mcp)
- [CodeRabbit: AI Code Reviews](https://www.coderabbit.ai/)

---

> **Note:** This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.
+1

# L4U_Blog

## What is L4U_Blog?

**L4U_Blog** is a modern, multi-user blogging platform designed for developers and community members to create, share, and discover articles. The platform supports Markdown editing, image uploads (including AI-generated images), dark/light mode, and social sharing. AI features powered by Gemini help with summaries, SEO, tags, and image generation. Built with Next.js and Supabase, L4U_Blog is a showcase of full-stack, AI-assisted web development.

---

## 🛠️ Tech Stack

- **TypeScript** / JavaScript
- **Next.js** (React, SSR, routing)
- **Tailwind CSS** (styling, dark/light mode)
- **Supabase** (PostgreSQL, Auth, Storage)
- **react-markdown**, **remark-gfm** (Markdown support)
- **Gemini CLI** (AI text/image features)
- **Cursor**, **Træ (TRAE)** (AI code editors)
- **CodeRabbit** (AI code review)
- **Jest**, **React Testing Library** (testing)
- **GitHub**, **Vercel** (deployment)

---

## 🧠 AI Integration Strategy

- **Code & Feature Generation:** Use AI editors (Cursor, Træ) and Gemini CLI to scaffold features, generate models, and routes from natural-language prompts. Context7 ensures up-to-date code and docs.
- **Testing Support:** Prompt AI to generate Jest/RTL tests for functions and components, covering both success and error scenarios.
- **Documentation & Comments:** Use AI for docstrings, inline comments, and README updates. Feed code context or API schemas to AI for accurate explanations.
- **Context-Aware Generation:** Use Context7 and MCP to ground AI in project specifics (file tree, DB schema, OpenAPI spec). Use Gemini CLI to query Supabase schema and generate code based on live DB/API.

---

## 🔒 In-Editor & PR Review Tooling

- **Cursor/Træ:** AI code completion and feature scaffolding in the editor.
- **CodeRabbit:** Automated, line-by-line AI reviews for every PR (suggests fixes, generates summaries, and commit messages).
- **GitHub:** Version control and collaboration; CodeRabbit is connected for PR reviews.

---

## 📝 Prompting Strategy

- **Feature Generation:**
  > Generate a Next.js API route `/api/posts/create` that handles creating a new blog post. It should validate the input fields (title and content) and save the post to Supabase, returning an error if validation fails.
- **Testing:**
  > Write a Jest test suite for the `loginUser` function, covering successful login (valid credentials), incorrect password, and missing fields errors. Mock Supabase Auth calls.
- **Context-Aware:**
  > (With Context7) Generate a SQL query to fetch all published posts by a given user from the Supabase schema.

---

## 📋 Capstone Planning

- Public GitHub repository: [favour-22/L4U_Blog](https://github.com/favour-22/L4U_Blog)
- This `README.md` with detailed project plan:
  - Project header & description
  - Tech stack
  - AI integration strategy
  - In-editor/PR review tooling
  - Prompting strategy

---

## 📚 References

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

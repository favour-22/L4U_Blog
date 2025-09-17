
# L4U_Blog

**L4U_Blog** is a multi-user blogging platform built for developers and community members to create, share, and discover articles. Designed as a full-stack capstone project, it incorporates modern web development practices along with AI-assisted development tools and workflows.

---

## 🌐 Project Overview

L4U_Blog offers:

- 🧑‍💻 **User Authentication** via Supabase Auth  
- 📝 **Post Creation & Sharing**: Users can write, publish, and read blog posts  
- 💬 **Comment System** for community interaction  
- 🌓 **Dark/Light Mode Toggle** for accessibility  
- 🧠 **AI-Assisted Development** integrated throughout the stack

This platform supports both knowledge sharing and personal portfolio building, showcasing real-world full-stack engineering and AI-enhanced workflows.

---

## 🧰 Tech Stack

### 🖥 Frontend
- **Next.js** (React-based framework) for SSR and routing  
- **Tailwind CSS** for utility-first styling and responsive UI  

### 🗃 Backend / Database
- **Supabase** (PostgreSQL)  
  - Authentication via **Supabase Auth**  
  - Real-time database operations  
  - Storage for blog content and user metadata  

### 🧠 AI Tools
- **Cursor** and **Træ** (TRAE): AI-assisted IDEs for writing code via instructions  
- **Gemini CLI**: Google's AI-powered CLI for generating code and querying the database via natural language  
- **CodeRabbit**: Automated AI code reviews in GitHub PRs  

### 🧪 Testing
- **Jest** and **React Testing Library** for unit and integration testing  

### 🚀 Deployment
- **Vercel** or **Supabase Hosting** for frontend/backend deployment  
- **GitHub** for version control (Repo: [favour-22/L4U_Blog](https://github.com/favour-22/L4U_Blog))  

---

## 🧠 AI Integration Strategy

L4U_Blog leverages AI tools across the development lifecycle:

### 🔧 Code & Feature Generation
- **AI-Powered Prompts** used to generate components, routes, and functions  
- Example prompt:  
  > “Generate a Next.js API route `/api/posts/create` that validates inputs and saves the post to Supabase.”

- **Gemini CLI** used for tasks like:
  - “Create Supabase table schema for blog posts”
  - “Generate login logic using Supabase Auth”

- **Context7** ensures prompts use the latest API docs and conventions

### 🧪 Testing Support
- AI generates test cases for:
  - Authentication workflows  
  - Blog post creation/validation  
  - Edge/error cases

- Example prompt:  
  > “Write Jest tests for loginUser including valid, invalid, and empty credential cases.”

### 🧾 Documentation & Comments
- Inline documentation and README sections generated using AI  
- Example:  
  > “Explain the purpose of this function/module”  

- AI tools keep in-code comments and README updated as development progresses

### 📊 Context-Aware Development
- **Context7** used to pull accurate docs per library/package  
- **Model Context Protocol (MCP)** enables AI to query live Supabase schema  
- Example usage:
  - “List all columns in `users` table”  
  - “Generate SQL to fetch posts by a user ID”

- For REST or GraphQL APIs, OpenAPI specs and schemas are provided to the AI to generate client functions

---

## 🛠 IDE & Code Review Tooling

### ✨ AI-Enabled IDEs
- **Cursor** and **Træ** provide smart suggestions, code completions, and AI-generated scaffolding
- Developers can describe functionality, and the IDE will generate corresponding code

### 🔍 Pull Request Reviews
- **CodeRabbit** reviews each PR with:
  - Line-by-line analysis
  - Suggestions for fixes or improvements
  - Summaries of commits and changes

- Reduces review time and improves code quality with AI precision

### 🔁 GitHub Integration
- Every PR triggers CodeRabbit analysis
- Gemini CLI and AI tools suggest commit messages based on the diff
- Clean, AI-reviewed code pushed with well-written PR summaries

---

## 🧠 Prompting Strategy


### Feature Example

```text
Generate a Next.js API route handler for /api/createPost that accepts title and content, validates them, and inserts a new row into the Supabase posts table.
```

### Test Example

```text
Write a Jest test suite for the loginUser function, covering successful login, incorrect password, and missing fields errors. Mock Supabase Auth calls.
```

> By including specific function names, fields, and framework context, we ensure highly relevant AI-generated code and tests.

---

## 🔮 Future Enhancements

* Support for image uploads in blog posts
* Rich text editor integration (e.g., TipTap or Quill)
* Enhanced search & tagging system
* User profiles & follower system
* AI-generated content recommendations

---


## 📂 Repository

🔗 GitHub Repo: [https://github.com/favour-22/L4U_Blog](https://github.com/favour-22/L4U_Blog)

---


## 🙏 Support the Project

If you find L4U_Blog useful or inspiring, consider [sponsoring me on GitHub](https://github.com/sponsors/favour-22) to help sustain future open-source work. Your support makes a big difference!

---


## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---
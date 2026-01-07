# 🤖 Universal Review Agent Toolkit

A language-agnostic, rubric-driven evaluation system designed for AI coding agents. This toolkit allows you to automate the review of student repositories (or any codebase) across any programming language based on a structured grading rubric.

---

## 🌟 Key Features
- **🌍 Language Agnostic**: Automatically identifies project types and tech stacks (Python, Java, Node.js, Go, Rust, etc.).
- **📋 Rubric-First Logic**: Analysis is driven entirely by the provided evaluation criteria, ensuring consistency and objectivity.
- **🔍 Automated Discovery**: Uses keyword-based scanning to pinpoint core architectural patterns and technologies.
- **📄 Standardized Reporting**: Generates clean, evidence-based markdown reports with code snippets.
- **🚨 Pre-flight Validation**: Built-in checks to ensure all required rubrics and templates are present before starting.

---

## 📂 Project Structure
```text
.
├── .agent/
│   └── workflows/
│       └── review-student-repo.md  <-- Main AI Workflow/Prompt
├── Review_Objectives/
│   ├── Example_Rubric_Template.md  <-- Use this to create your rubrics
│   └── Review_Report_Template_Universal.md <-- Base reporting structure
└── docs/
    └── Agent_Initialization_Guide.md <-- Technical setup guide
```

---

## 🛠️ Getting Started: AI Agent Setup

This toolkit is optimized for the latest AI agentic workflows. Follow the steps below for your preferred environment:

### 🎮 For Antigravity / Google Advanced Coding
1. **Clone** this repository into your project root.
2. The agent will automatically detect the `.agent/workflows/review-student-repo.md` file.
3. Simply type `/review-student-repo` in the chat to see the parameter requirements.

### 🌊 For Windsurf / Flow-based Agents
1. Ensure the `.agent` directory is in the root of your workspace.
2. The agent will index the markdown files; mention "review student repo workflow" to activate it.

### ⚡ For Cursor / GitHub Copilot
1. Copy the contents of `.agent/workflows/review-student-repo.md` into your "Rules for AI" or `.cursorrules` file.
2. Reference the `Review_Objectives/` folder as context when starting a review.

---

## 🚀 How to Use

To trigger a review, use the following command structure:

**/review-student-repo [repo_url] [student_name] [rubric_path]**

### Execution Stages:
1. **Validation**: The agent checks if your rubric exists and if the report template is available.
2. **Discovery**: The agent identifies the language (e.g., "This is a TypeScript project using Vite") and scans for keywords defined in your rubric.
3. **Analysis**: The agent compares the code against your rubric criteria, looking for "Evidence" (code snippets).
4. **Reporting**: A detailed evaluation report is generated in the `Module_Reviews/` folder.

---

## 📝 Creating Your Own Rubrics

The agent's power depends on how well you define your rubric. For the best results, always include a **"Keywords for Search"** section.

**Example Rubric Snippet:**
```markdown
### 1. State Management
- **Criteria**: Full use of Redux or Context API.
- **Keywords for Search**: `createSlice`, `useContext`, `dispatch`, `Provider`
```

---

## 🤝 Contributing
Feel free to submit Pull Requests for new language templates or improvements to the agnostic discovery logic!

## 📜 License
MIT License - See [LICENSE](LICENSE) for details.

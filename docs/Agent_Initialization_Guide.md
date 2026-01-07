# Universal Review Agent: Initialization Guide

This toolkit allows you to initialize a specialized AI agent capable of reviewing programming repositories across any language or project type based on a provided rubric.

## 📦 Package Contents
- `.agent/workflows/review-student-repo.md`: The main logic/prompt for the agent.
- `Review_Objectives/Review_Report_Template_Universal.md`: The base reporting structure.
- `Review_Objectives/Example_Rubric_Template.md`: A reference for creating your own rubrics.

## 🚀 Setup Instructions

### 1. Initialize the Package
Copy the `Universal_Review_Agent_Toolkit` directory into your workspace root.

### 2. Push to GitHub (Optional)
If you want to share this agent across teams:
```bash
git init
git add .
git commit -m "Initialize Universal Review Agent Toolkit"
git remote add origin [your-repo-url]
git push -u origin main
```

### 3. Using the Agent
Once the agent has access to these files, you can trigger a review using the following command in the chat:

**/review-student-repo [repo_url] [student_name] [rubric_path]**

### 📋 Rubric Requirements
For the agent to work effectively, your rubric file should include a **"Keywords for Search"** section for each objective. This helps the agent automate the technical discovery phase.

Example:
```markdown
### 1. Concurrency
- Keywords for Search: `async`, `await`, `Thread`, `Promise.all`
```

## 🛠️ Customization
To tailor the agent further, modify the `Review_Report_Template_Universal.md` to match your organization's branding or specific reporting requirements.

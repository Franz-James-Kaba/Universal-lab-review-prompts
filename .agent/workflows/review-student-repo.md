description: >
  A universal, language-agnostic workflow for evaluating student GitHub repositories. 
  This agent-driven process dynamically adapts to any programming language or project structure by parsing a 
  user-provided grading rubric. It automates technical discovery via keyword-based scanning, performs deep 
  architectural analysis aligned with specific grading criteria, and generates a standardized evaluation report. 
  Includes automated pre-flight checks to ensure all required documentation is present before initiating the review.
---

# /review-student-repo [repo_url] [student_name] [rubric_path]

This workflow automates the evaluation of student projects using the established rubric and technical standards.

## 1. Environment Setup & Validation
1. **Pre-flight Check**:
   - Verify `[rubric_path]` exists. 
   - Verify `Review_Objectives/Review_Report_Template_Universal.md` exists.
   - > [!IMPORTANT]
   - > If either file is missing, **STOP** and use `notify_user` to ask the user to provide the missing rubric or template file before continuing.

2. Create a workspace directory for the student if it doesn't exist: `mkdir -p "Module_Reviews/{student_name}"`
3. Clone the repository into the review folder:
   ```bash
   git clone [repo_url] "Module_Reviews/{student_name}/repo"
   ```
4. Read the provided grading rubric and report template.

## 2. Technical Discovery
// turbo
1. Extract key technologies and keywords from `[rubric_path]`.
2. Scan for identified technologies in the repository:
   - Identify project type by looking for standard build/config files (e.g., `package.json`, `pom.xml`, `requirements.txt`, `go.mod`, `Cargo.toml`).
   - Use `grep` or `find` to locate core source files based on the project structure.
   - ```bash
     # General scan based on rubric keywords
     grep -rE "keyword1|keyword2|keyword3" "Module_Reviews/{student_name}/repo"
     ```
3. Evaluate dependency management and project organization.

## 3. Deep Analysis
1. **Criteria Alignment**: Systematically evaluate the codebase against each section of the provided `[rubric_path]`.
2. **Evidence Collection**: Extract code snippets and architectural patterns that demonstrate compliance or failure for each rubric item.
3. **Quality Assessment**: Apply the specific scoring criteria defined in the rubric.

## 4. Report Generation
1. Initialize the evaluation report based on the structure of `[rubric_path]`.
2. Populate the **Scorecard** with evidence-based ratings derived from the rubric.
3. Provide **Technical Analysis** with specific code snippets as proof for each criteria.
4. Save the final report to: `Module_Reviews/{student_name}_Review.md`

## 5. Summary & Housekeeping
1. Update the `Module{module_num}_Summary_Report.md` with the new student's score and category.
2. Update the `Top_Performer_Showcase.md` if the student qualifies as "Elite" (95+ score).
3. Notify the user of completion with a summary of key findings.

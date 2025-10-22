# Get Started with Kiro

What is Kiro and why choose kiro?

1. Download Kiro from https://kiro.dev/.

2. Review Kiro Pricing model. Its billing is based on credits.

   - https://kiro.dev/pricing/

3. Create a new project folder and open it with Kiro

```
mkdir kiro-demo-22
kiro kiro-demo-22
```

5. There are many ways to login Kiro.

6. On the Kiro side bar on the left:
   - Agent Steering
   - Agent Hook
   - Specs
   - MCP Servers

## A. Spec-Driven Workflow

1. Turn off the Autopilot, so that we can use multiple prompts to refine spec files.

2. Share with Kiro what we are trying to build in this project. Enter following prompts one by one.

   > I would like to build a user-friendly web portal with QR code related functions.

   > What would be the most common QR code features asked by users?

   > Let's focus on the basic features first: QR code generation from text and URLs; QR code decoding from uploaded images.

Kiro generates `requirements.md` file in the `.kiro/specs/` folder, which contians requirements with one or more user stories. With more prompts, Kiro will refine the `requirements.md` file.

Note: It's worth time to go through the requirements.md file in details.

3. Ask Kiro to suggest design.

   > Let's move to design.

Kiro generates `design.md` file. This design focus on a single web layer since we only asked for basic features. Assume we would like the portal to include advanced features like dynamic QR code, we will need a backend to support these features. Thus we would like the implementation to be separated into frontend and backend.

> Use React (TypeScript) for frontend and Python with FastAPI for backend.

Kiro will update the `design.md` file and change the architecture to include both frontend and backend.

4. Let Kiro generate task list to guide the implementation.

> Should I continue with the implementation plan or web UI design first?

Kiro will suggest to continue with implementation plan.

> Continue with the implementation plan.

Kiro generates the `tasks.md` file.

### Get Familiar with Kiro IDE

- What is the differences: Vibe vs Spec?
- How many credit is consumed and what is my total credits?

- On the Chat side bar on the right

  - Chat: Use # to specify file, upload image
  - Change model but will cost more.
  - Auto-Pilot

- Tasks in Queue

## B. Specs, Agent Steering, Agent Hook

Go to Kiro Left Side Pane.

### Specs

1. Clicks on the first item in SPECS.

Kiro has generated `requirements.md`, `design.md` and `tasks.md` files in above section. The `requirement.md` file is the center of the specs for this project.

### Agent Steering

The function of Agent Steering is similar to the `CLAUDE.md` file, if you are using Claude Code.

2. Click on "Generate Steering Docs" button.

- Kiro will start a new chat session to generate 3 files: `product.md`, `structure.md`, `tech.md`. Review each of the file.

> For backend, create an virtual environment and use it while running backed code. Use .venv folder instead of venv folder for virtual environment.

Kiro will update the `tech.md` file accordingly and rename the `vevn` folder name to `.venv`.

### Agent Hook

What is Agent Hook?

- Monitor for events and send a prompt to complete a routine task. The hook can be triggered by a file event, e.g. file created, saved or deleted. It can also be manually triggered.

3. Create following sample hooks.

Example 1: Auto Translate Generator

- Create a new Agent Hook with following description

```
Monitor changes to files containing user-facing text content (such as json, -yaml, or other localization files) in the primary language. When changes are detected, automatically identify the new or modified text and generate translations for all configured target languages. Ensure translations maintain proper context and meaning while adhering to locale-specific conventions.
```

- Disable it after creating it since we dont need it at the moment.

Example 2: Code Quality Analyzer

- Create a new Agent Hook with following description

```
Monitors source code files for changes and analyzes modified code for potential improvements, including code smells, design patterns, and best practices. Generates suggestions for improving code quality while maintaining existing functionality.
```

Example 3: Documentation Sync

- Create a new Agent Hook with following description

```
Listens to source file changes and triggers documentation updates in README or docs folder.
```

4. Go back to Explorer left side pane.

- Review that hooks are saved in `.kiro/hooks` folder.

### MCP

MCP servers can be added either at project level or computer level. The JSON file format is similar to other IDE.

- .kiro/settings/mcp.json
- ~/.kiro/settings/mcp.json

## C. Backend Implementation

1. Go back to `tasks.md` file. Click on "Start task" link above Task 1 to start implementation. Kiro will first read the steering documents before working on the task.

   - While Kiro is implmeneting task 1, it will ask for permissions to run commands.

   - All commands are run in the terminal, providing a clear insights on what have been executed.

2. Check the `Task List` to see that agent hook `Code Quality Analyzer` is queued to be executed next.

Kiro will run the code analysis and generate an output. The output is currently not saved in anywhere.

> Are you analysis documented somewhere in file(s)?
> Pls document your analysis in a file in the /docs folder in project root. Add datetime timestamp YYYYMMDDTHHMMSS in the file name.

3. Update the agent hook `Code Quality Analyzer` to save the analysis to `docs/` folder.

```
Monitors source code files for changes and analyzes modified code for potential improvements, including code smells, design patterns, and best practices. Generates suggestions for improving code quality while maintaining existing functionality. Save your analysis in a file `code-review-{datetime}.md` file in `docs/` foder in project root.

	...

6. Save your analysis in a file `code-review-{datetime}.md` file in `docs/` foder in project root.

```

### Create Tests for Backend

4. Create a comprehensive tests for the backend.

> Create comprehensive tests for all existing endpoints for the backend.

5. Run the tests and save test result.

> Run the tests and document the test results in a file `test-results-{datetime}.md` file in the /docs folder in project root?

### Add Agent Hook to Perform Tests

6. Create a new Agent Hook to update and run tests for backend tests. Set it as a Manual trigger.

```
Update the comprehensive tests in `backend/tests/` folder to cover all all existing endpoints. Run the tests and document the test results in a file `test-results-{datetime}.md` file in the /docs folder in project root.
```

### Add Agent Steering

After we perform code review and tests, we would like Kiro to be aware of the results before it make further code changes.

7. Create a new Agent Steering `docs-guide`, enter following text, and click on `Refine` button for Kiro to refine it. Accept the changes to the file.

```
<!------------------------------------------------------------------------------------

Add Rules to this file or a short description and have Kiro refine them for you:

------------------------------------------------------------------------------------->

---
inclusion: fileMatch
fileMatchPattern: "docs/*.md"
---

# Project Documentation Guidance

All code review and test result files are stored in the `/docs` folder at the project root.

**Instructions for Kiro:**

- Before continuing any implementation or review, always check the `/docs` folder.
- Locate the latest code review and test result file by filename date or lexicographical order.
- Use only the most recent file of each type (e.g., `code-review-YYYY-MM-DDTHHMMSS.md`, `test-results-YYYY-MM-DDTHHMMSS.md`) to inform your actions and provide context.
- Update the file to indicate that you have process it.
- Ignore older files or processed files unless otherwise instructed.
- Attend to the highest priority issues only.

This ensures that all code changes and decisions are made with reference to the latest available reviews and test outcomes.
```

### Complete Endpoint for QR Generation

8. Go back to `tasks.md` file. Implement backend QR code generation service and endpoint.
   - Observe that it will queue the Document Update agent hook, and

### Manual Testing Backend

9. Start a new terminal session to run the backend.

```bash
cd backend
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

10. Test the QR code generation API endpoint.
    - Decode the image at https://base64.guru/converter/decode/image

## D. Frontend Implementation

1. Go back to `tasks.md` file. Look for tasks related to "Set up frontend project structure and dependencies" and start it by clicking on the `Start task` link above it.

2. Create tests for frontend.

> Shall we create tests for frontend using Jest or some similar tools? Create the tests in frontend/tests/ folder.

3. Create a new Agent Hook for frontend testing. Set it to manual triggering.

```
The frontend/tests/ folder contains tests for the code in frontend/. Update the comprehensive tests in `frontend/tests/` folder to cover all all existing codes. Run the tests and document the test results in a file `test-results-{datetime}.md` file in the /docs folder in project root.
```

4. Start the task which implements the QR code generation in frontend.

   - Tasks will be queued when we start multiple tasks.

5. Start a new terminal session to run the frontend.

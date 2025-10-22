# Get Started with Kiro

## Introduction

### What is Kiro?

Kiro is an AI-powered IDE (Integrated Development Environment) designed to accelerate software development through intelligent automation and spec-driven workflows. It combines the capabilities of modern AI models with traditional development tools to help you build applications faster and more efficiently.

### Why Choose Kiro?

- **Spec-Driven Development**: Define requirements, design, and tasks before coding
- **Intelligent Automation**: AI agents handle routine tasks and code generation
- **Agent Hooks**: Automate workflows like testing, documentation, and code review
- **Agent Steering**: Guide AI behavior with project-specific instructions
- **MCP Integration**: Extend functionality with Model Context Protocol servers
- **Transparent Execution**: All commands run in visible terminals

### Key Features Overview

- **Vibe Mode**: Quick, conversational interactions for rapid development
- **Spec Mode**: Structured, specification-driven approach for complex projects
- **Auto-Pilot**: Let Kiro execute multiple steps autonomously
- **Manual Control**: Review and approve each step individually
- **Credit-Based Pricing**: Pay only for what you use

### Prerequisites

Before starting, ensure you have:

- **Operating System**: macOS, Windows, or Linux
- **Node.js**: Version 18 or higher (for frontend projects)
- **Python**: Version 3.9 or higher (for backend projects)
- **Git**: For version control
- **Internet Connection**: For AI model access

---

## Part 1: Setup & First Steps

### 1.1 Installation

Download and install Kiro from the official website:

```bash
# Visit https://kiro.dev/ and download for your platform
```

Follow the installation wizard for your operating system.

### 1.2 Understanding Pricing

Review Kiro's pricing model before starting. Kiro uses a credit-based billing system:

- Visit [https://kiro.dev/pricing/](https://kiro.dev/pricing/)
- Credits are consumed based on:
  - AI model usage (different models cost different amounts)
  - Number of operations performed
  - Complexity of tasks

**Tip**: Start with a free trial or small credit package to evaluate Kiro for your needs.

### 1.3 Create Your First Project

Create a new project folder and open it with Kiro:

```bash
# Create project directory
mkdir kiro-demo

# Navigate to the directory
cd kiro-demo

# Open with Kiro (or use File > Open Folder in Kiro)
kiro .
```

**Alternative**: Launch Kiro and use `File > Open Folder` to select your project directory.

### 1.4 Authentication

When you first launch Kiro, you'll need to authenticate. Kiro supports multiple login methods:

- **Email/Password**: Standard account login
- **GitHub**: OAuth integration with GitHub
- **Google**: OAuth integration with Google
- **SSO**: Enterprise single sign-on (for team plans)

Choose your preferred method and complete the authentication flow.

### 1.5 Understanding the Kiro Interface

#### Left Sidebar (Project Tools)

- **Agent Steering**: Define project-specific instructions for AI agents
- **Agent Hooks**: Set up automated workflows triggered by file events
- **Specs**: View and manage requirements, design, and task specifications
- **MCP Servers**: Configure Model Context Protocol extensions

#### Right Panel (Chat & Interaction)

- **Chat Interface**: Interact with AI using natural language
- **File References**: Use `#` to reference specific files in chat
- **Image Upload**: Upload screenshots or diagrams for context
- **Model Selection**: Choose different AI models (costs vary)
- **Auto-Pilot Toggle**: Switch between manual approval and autonomous execution

#### Bottom Panel

- **Terminal**: View command execution in real-time
- **Task Queue**: See queued agent hook executions
- **Credit Usage**: Monitor your credit consumption

### 1.6 Vibe vs Spec Modes

**Vibe Mode**:

- Quick, conversational interactions
- Best for small changes, bug fixes, or exploration
- Less structured, more flexible
- Lower cognitive overhead

**Spec Mode**:

- Structured, specification-driven workflow
- Best for complex projects or team collaboration
- Generates `requirements.md`, `design.md`, and `tasks.md`
- More organized and traceable

**When to use which?**

- Use **Vibe** for prototypes, quick fixes, and learning
- Use **Spec** for production projects, team work, and complex systems

---

## Part 2: Your First Project (Spec-Driven Workflow)

In this tutorial, we'll build a **QR Code Web Portal** with the following features:

- Generate QR codes from text and URLs
- Decode QR codes from uploaded images
- Modern web interface with React frontend
- RESTful API backend with Python/FastAPI

### 2.1 Disable Auto-Pilot for Learning

Turn off Auto-Pilot so you can review each step and understand what Kiro is doing:

- Click the **Auto-Pilot** toggle in the right panel to disable it
- This allows you to approve each action manually

**Why disable it?**: During learning, it's valuable to see each step and understand Kiro's reasoning.

### 2.2 Define Initial Requirements

Start a conversation with Kiro to define what you want to build. Enter these prompts **one by one**:

**Prompt 1:**

```
I would like to build a user-friendly web portal with QR code related functions.
```

**Prompt 2:**

```
What would be the most common QR code features asked by users?
```

Kiro will suggest common features like:

- QR code generation (text, URLs, contact info)
- QR code scanning/decoding
- Customization (colors, logos, error correction)
- Bulk generation
- Analytics and tracking

**Prompt 3:**

```
Let's focus on the basic features first: QR code generation from text and URLs, and QR code decoding from uploaded images.
```

**Result**: Kiro generates a `requirements.md` file in `.kiro/specs/` folder containing:

- Project overview
- User stories
- Functional requirements
- Non-functional requirements

**Important**: Take time to review the `requirements.md` file carefully. This is the foundation of your project.

### 2.3 Refine the Design

Ask Kiro to suggest a system design:

**Prompt 4:**

```
Let's move to design.
```

**Result**: Kiro generates a `design.md` file with:

- System architecture
- Technology stack
- Component breakdown
- Data flow

**Initial Design Issue**: Since we only asked for basic features, Kiro might suggest a single-layer web application. However, if we want to add advanced features later (like dynamic QR codes, analytics), we need a proper backend.

**Prompt 5:**

```
Use React with TypeScript for the frontend and Python with FastAPI for the backend. Separate the implementation into frontend and backend layers.
```

**Result**: Kiro updates `design.md` with:

- Frontend: React (TypeScript) single-page application
- Backend: FastAPI REST API with Python
- Clear separation of concerns
- API contract between layers

### 2.4 Generate Implementation Tasks

Ask Kiro to create a detailed task list:

**Prompt 6:**

```
Should I continue with the implementation plan or web UI design first?
```

Kiro will likely suggest continuing with the implementation plan.

**Prompt 7:**

```
Continue with the implementation plan.
```

**Result**: Kiro generates a `tasks.md` file containing:

- Numbered task list
- Each task with description and acceptance criteria
- Logical ordering (backend setup → API endpoints → frontend setup → UI components)
- Testing tasks

### 2.5 Review Generated Specifications

Navigate to the **Specs** section in the left sidebar. You should see:

- ✅ `requirements.md` - What we're building and why
- ✅ `design.md` - How we're building it
- ✅ `tasks.md` - Step-by-step implementation guide

**Tip**: These files are editable. You can manually refine them before implementation.

---

## Part 3: Core Kiro Concepts

### 3.1 Specs: The Foundation of Your Project

**Specs** are structured markdown files that define your project:

**`requirements.md`** - The "What and Why"

- Business requirements
- User stories
- Success criteria
- Constraints

**`design.md`** - The "How"

- Architecture decisions
- Technology stack
- Component structure
- Data models

**`tasks.md`** - The "Implementation Roadmap"

- Ordered task list
- Each task is independently implementable
- Clear acceptance criteria
- Clickable "Start task" links

**Best Practice**: Treat specs as living documents. Update them as your project evolves.

### 3.2 Agent Steering: Project Instructions

**Agent Steering** provides project-specific instructions to guide AI behavior. Think of it as a `CLAUDE.md` or `.cursorrules` file.

#### Generate Steering Documents

1. Click **Agent Steering** in the left sidebar
2. Click **"Generate Steering Docs"** button

Kiro will start a new chat session and generate three files in `.kiro/steering/`:

**`product.md`** - Product context

- What problem you're solving
- Target audience
- Key features and priorities

**`structure.md`** - Project structure

- Folder organization
- File naming conventions
- Module boundaries

**`tech.md`** - Technical guidelines

- Technology stack details
- Coding standards
- Dependencies and tools

#### Customize Steering Documents

Example: Update Python virtual environment preferences:

**Prompt:**

```
For backend, create a virtual environment and use it while running backend code. Use .venv folder instead of venv folder for virtual environment.
```

**Result**: Kiro updates `tech.md` and will use `.venv` consistently throughout the project.

#### Create Custom Steering Rules

You can create additional steering files for specific contexts:

**Example**: Create `.kiro/steering/docs-guide.md`:

```markdown
---
inclusion: fileMatch
fileMatchPattern: "docs/*.md"
---

# Project Documentation Guidance

All code review and test result files are stored in the `/docs` folder.

**Instructions for Kiro:**

- Before continuing any implementation, check `/docs` for latest reviews
- Locate the most recent file by timestamp
- Address only the highest priority issues
- Update files to mark them as processed
```

### 3.3 Agent Hooks: Automated Workflows

**Agent Hooks** monitor for events and trigger automated tasks. They can respond to:

- File created
- File saved
- File deleted
- Manual trigger

#### Example 1: Auto Translation Generator

**Use Case**: Automatically translate UI text when localization files change.

1. Click **Agent Hooks** in the left sidebar
2. Click **"Create New Hook"**
3. Enter the description:

```
Monitor changes to files containing user-facing text content (such as .json, .yaml, or other localization files) in the primary language. When changes are detected, automatically identify the new or modified text and generate translations for all configured target languages. Ensure translations maintain proper context and meaning while adhering to locale-specific conventions.
```

4. **Disable** the hook after creation (we don't need it for this tutorial)

#### Example 2: Code Quality Analyzer

**Use Case**: Automatically review code quality when files change.

Create a new hook with this description:

```
Monitors source code files for changes and analyzes modified code for potential improvements, including code smells, design patterns, and best practices. Generates suggestions for improving code quality while maintaining existing functionality. Save your analysis in a file named code-review-{datetime}.md in the docs/ folder in project root, where {datetime} is formatted as YYYYMMDDTHHMMSS.
```

**Key Addition**: Notice we specified where to save the output. Without this, the analysis would only display in chat.

#### Example 3: Documentation Sync

**Use Case**: Keep documentation in sync with code changes.

```
Listens to source file changes and triggers documentation updates in README or docs folder. Ensure documentation accurately reflects current implementation.
```

#### Managing Hooks

- **View Hooks**: Navigate to `.kiro/hooks/` folder in the Explorer
- **Enable/Disable**: Toggle hooks on/off as needed
- **Trigger Type**: Set to automatic (file events) or manual
- **Task Queue**: View queued hook executions in bottom panel

### 3.4 MCP Servers: Extending Kiro

**MCP (Model Context Protocol)** servers extend Kiro's capabilities with custom tools and integrations.

#### Configuration Levels

**Project-level**: `.kiro/settings/mcp.json`

- Specific to current project
- Not shared across projects

**Computer-level**: `~/.kiro/settings/mcp.json`

- Available in all projects
- Shared configuration

#### Example MCP Configuration

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/username/projects"
      ]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "your-token-here"
      }
    }
  }
}
```

**Tip**: Search for available MCP servers at [https://github.com/modelcontextprotocol](https://github.com/modelcontextprotocol)

---

## Part 4: Backend Implementation

### 4.1 Start First Task

1. Open the `tasks.md` file from the Specs sidebar
2. Find the first backend task (usually "Set up backend project structure")
3. Click the **"Start task"** link above the task

**What happens**:

- Kiro reads all steering documents first
- Begins implementing the task
- Requests permission for commands (creating folders, installing packages)
- Shows all commands in the terminal

**Important**: Review each command before approving. This helps you understand what's being done.

### 4.2 Monitor Task Execution

Watch the terminal output to see:

- Directory creation
- Virtual environment setup
- Package installations
- File generation

**Expected structure**:

```
backend/
├── .venv/               # Python virtual environment
├── app/
│   ├── __init__.py
│   ├── main.py         # FastAPI application
│   ├── models/         # Data models
│   ├── routes/         # API endpoints
│   └── services/       # Business logic
├── requirements.txt     # Python dependencies
└── tests/              # Test files
```

### 4.3 Code Quality Hook Execution

Check the **Task Queue** in the bottom panel. You should see:

- ✓ Task 1: Backend setup (completed)
- ⟳ Agent Hook: Code Quality Analyzer (running)

The Code Quality Analyzer hook was triggered automatically when files were created.

**Verify output**:

1. Navigate to `docs/` folder
2. Find `code-review-{timestamp}.md`
3. Review the analysis

**What to look for**:

- Code smells
- Best practice violations
- Suggested improvements
- Security concerns

### 4.4 Create Backend Tests

Create comprehensive tests for the backend API:

**Prompt:**

```
Create comprehensive tests for all existing endpoints in the backend. Use pytest and organize tests in backend/tests/.
```

**Expected structure**:

```
backend/tests/
├── __init__.py
├── conftest.py          # Pytest configuration
├── test_health.py       # Health check endpoint tests
└── test_qr_generation.py # QR generation tests (when implemented)
```

### 4.5 Run Tests and Document Results

**Prompt:**

```
Run the backend tests and document the test results in a file named test-results-{datetime}.md in the docs/ folder in project root, where {datetime} is formatted as YYYYMMDDTHHMMSS.
```

**Expected output**:

- Test execution in terminal
- Test results file in `docs/`
- Summary of passed/failed tests

### 4.6 Create Backend Test Hook

Create an Agent Hook for automated testing:

1. Click **Agent Hooks** in left sidebar
2. Create new hook with description:

```
Update the comprehensive tests in backend/tests/ folder to cover all existing endpoints. Run the tests and document the test results in a file named test-results-{datetime}.md in the docs/ folder in project root, where {datetime} is formatted as YYYYMMDDTHHMMSS.
```

3. Set trigger type to **Manual** (we'll trigger it explicitly)

**Why manual?**: Running full test suites on every file change can be expensive. Manual triggering gives you control.

### 4.7 Implement QR Code Generation Endpoint

1. Return to `tasks.md`
2. Find the task: "Implement backend QR code generation service and endpoint"
3. Click **"Start task"**

**What Kiro will do**:

- Install QR code library (e.g., `qrcode`, `python-qrcode`)
- Create service layer for QR generation
- Implement API endpoint (`POST /api/qr/generate`)
- Add input validation
- Update tests

**Observe the task queue**:

- Code Quality Analyzer hook will queue automatically
- Documentation Sync hook may also trigger

### 4.8 Manual Backend Testing

Start the backend server to test manually:

```bash
# Open a new terminal
cd backend

# Activate virtual environment
source .venv/bin/activate

# Install dependencies (if not already done)
pip install -r requirements.txt

# Start the server
uvicorn app.main:app --reload
```

**Expected output**:

```
INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
INFO:     Started reloader process
INFO:     Started server process
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

**Test the health endpoint**:

```bash
curl http://127.0.0.1:8000/health
```

**Test QR code generation**:

```bash
curl -X POST http://127.0.0.1:8000/api/qr/generate \
  -H "Content-Type: application/json" \
  -d '{"data": "https://kiro.dev", "size": 10}'
```

**Result**: You'll receive a JSON response with a base64-encoded image:

```json
{
  "image": "data:image/png;base64,iVBORw0KGgoAAAANS..."
}
```

**Decode the image**: Visit [https://base64.guru/converter/decode/image](https://base64.guru/converter/decode/image) and paste the base64 string to view the QR code.

### 4.9 Implement QR Code Decoding Endpoint

Continue with the next task in `tasks.md`:

**Prompt** (or click "Start task"):

```
Implement the QR code decoding endpoint that accepts an uploaded image and returns the decoded text.
```

**Expected implementation**:

- Install decoding library (e.g., `pyzbar`, `opencv-python`)
- Create decoding service
- Implement API endpoint (`POST /api/qr/decode`)
- Handle file uploads
- Return decoded text or error

**Test the decoding endpoint**:

```bash
curl -X POST http://127.0.0.1:8000/api/qr/decode \
  -F "file=@path/to/qr-code.png"
```

---

## Part 5: Frontend Implementation

### 5.1 Set Up Frontend Project

1. Go back to `tasks.md`
2. Find: "Set up frontend project structure and dependencies"
3. Click **"Start task"**

**What Kiro will do**:

- Create React app with TypeScript
- Set up Vite (or Create React App)
- Install dependencies (React, TypeScript, Axios)
- Configure build tools
- Create basic folder structure

**Expected structure**:

```
frontend/
├── node_modules/
├── public/
├── src/
│   ├── components/      # React components
│   ├── services/        # API client
│   ├── types/          # TypeScript types
│   ├── App.tsx
│   └── main.tsx
├── package.json
├── tsconfig.json
└── vite.config.ts
```

### 5.2 Create Frontend Tests

**Prompt:**

```
Shall we create tests for the frontend using Jest and React Testing Library? Create the tests in frontend/tests/ folder.
```

**What Kiro will install**:

- `@testing-library/react`
- `@testing-library/jest-dom`
- `@testing-library/user-event`
- `vitest` (if using Vite) or `jest`

**Expected test structure**:

```
frontend/tests/
├── setup.ts                    # Test configuration
├── components/
│   ├── QRGenerator.test.tsx
│   └── QRDecoder.test.tsx
└── services/
    └── api.test.ts
```

### 5.3 Create Frontend Test Hook

Create an Agent Hook for frontend testing:

```
The frontend/tests/ folder contains tests for the code in frontend/. Update the comprehensive tests in frontend/tests/ folder to cover all existing code. Run the tests and document the test results in a file named test-results-frontend-{datetime}.md in the docs/ folder in project root, where {datetime} is formatted as YYYYMMDDTHHMMSS.
```

Set trigger type to **Manual**.

### 5.4 Implement QR Code Generator Component

1. Find the task in `tasks.md`: "Implement QR code generator UI component"
2. Click **"Start task"**

**What Kiro will create**:

- `QRGenerator.tsx` component
- Input form for text/URL
- API integration with backend
- Display generated QR code
- Download functionality

**Expected features**:

- Text input field
- "Generate" button
- Loading state
- Error handling
- Display QR code image
- Download button

### 5.5 Implement QR Code Decoder Component

Continue with the next task:

**What Kiro will create**:

- `QRDecoder.tsx` component
- File upload input
- API integration with backend
- Display decoded text

**Expected features**:

- File upload (drag-and-drop or button)
- Image preview
- "Decode" button
- Display decoded text
- Error handling

### 5.6 Implement Main App Layout

**Prompt:**

```
Create the main App component that integrates both QR Generator and QR Decoder with a clean, responsive layout.
```

**What Kiro will create**:

- Navigation/tabs between generator and decoder
- Responsive design (mobile-friendly)
- Styling (CSS/Tailwind/Material-UI)
- Error boundaries

### 5.7 Run the Frontend

Start the frontend development server:

```bash
# Open a new terminal (keep backend running)
cd frontend

# Install dependencies (if not already done)
npm install

# Start development server
npm run dev
```

**Expected output**:

```
  VITE v5.0.0  ready in 500 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

**Test the application**:

1. Open [http://localhost:5173/](http://localhost:5173/) in your browser
2. Test QR code generation:
   - Enter text or URL
   - Click "Generate"
   - Verify QR code displays
   - Try downloading
3. Test QR code decoding:
   - Upload a QR code image
   - Click "Decode"
   - Verify decoded text displays

### 5.8 Handle Task Queue

When starting multiple tasks, they will queue automatically:

- View the queue in the bottom panel
- Tasks execute sequentially
- Agent hooks trigger after task completion
- You can cancel queued tasks if needed

---

## Part 6: Advanced Topics

### 6.1 CORS Configuration

If you encounter CORS errors when the frontend calls the backend:

**Prompt:**

```
The frontend at http://localhost:5173 is getting CORS errors when calling the backend at http://127.0.0.1:8000. Please configure CORS properly in the FastAPI backend.
```

**Expected fix**:

```python
# backend/app/main.py
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost:5173"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

### 6.2 Environment Variables

Create environment configuration files:

**Backend** (`.env`):

```bash
APP_NAME="QR Code Portal"
DEBUG=True
CORS_ORIGINS=http://localhost:5173
```

**Frontend** (`.env`):

```bash
VITE_API_URL=http://127.0.0.1:8000
```

**Prompt:**

```
Configure the application to use environment variables for API URLs and other configuration. Create .env files for both frontend and backend.
```

### 6.3 Production Build

**Build frontend**:

```bash
cd frontend
npm run build
```

**Build backend** (containerize):

```bash
cd backend
docker build -t qr-portal-backend .
```

**Prompt:**

```
Create a Dockerfile for the backend and docker-compose.yml to run both frontend and backend together.
```

### 6.4 Custom Styling

**Prompt:**

```
Improve the UI styling using Tailwind CSS. Add a modern color scheme, better spacing, and responsive design improvements.
```

### 6.5 Error Handling & Validation

**Prompt:**

```
Add comprehensive error handling and input validation:
- Frontend: Validate file types and sizes before upload
- Backend: Add request validation with Pydantic models
- Display user-friendly error messages
```

### 6.6 Performance Optimization

**Prompt:**

```
Optimize the application performance:
- Frontend: Add lazy loading for components
- Backend: Add caching for frequently generated QR codes
- Both: Implement request/response compression
```

---

## Troubleshooting & Tips

### Common Issues

#### Issue: "Permission denied" when running commands

**Solution**:

- Ensure you have proper file system permissions
- On Mac/Linux, you may need to use `chmod +x` for scripts
- Check if folders are write-protected

#### Issue: Backend dependencies fail to install

**Solution**:

```bash
# Upgrade pip first
python3 -m pip install --upgrade pip

# Try installing again
pip install -r requirements.txt

# If specific package fails, install it separately
pip install <package-name>
```

#### Issue: Frontend port already in use

**Solution**:

```bash
# Kill process on port 5173
lsof -ti:5173 | xargs kill -9

# Or use a different port
npm run dev -- --port 3000
```

#### Issue: "Module not found" errors in TypeScript

**Solution**:

- Check `tsconfig.json` path mappings
- Ensure imports use correct paths
- Restart TypeScript server in IDE

#### Issue: QR code decoding not working

**Solution**:

- Ensure image is a valid QR code
- Check image format (PNG, JPG supported)
- Verify `pyzbar` dependencies are installed (may need system libraries)

### Performance Tips

1. **Monitor Credit Usage**: Check the bottom panel regularly to avoid unexpected costs
2. **Use Vibe Mode for Small Changes**: Don't create full specs for minor tweaks
3. **Disable Unused Hooks**: Hooks consume credits when triggered
4. **Choose Appropriate Models**: Smaller models for simple tasks, larger for complex reasoning

### Best Practices

1. **Review Generated Code**: Always review code before accepting, especially for security-sensitive areas
2. **Keep Specs Updated**: Update `requirements.md`, `design.md`, and `tasks.md` as your project evolves
3. **Use Version Control**: Commit regularly to track changes and enable rollbacks
4. **Test Incrementally**: Don't wait until the end to test; validate each component as it's built
5. **Document Decisions**: Use steering docs to capture important architectural decisions

### Getting Help

- **Kiro Documentation**: [https://kiro.dev/docs](https://kiro.dev/docs)
- **Community Forum**: Check for similar issues and solutions
- **Support**: Contact Kiro support if you encounter bugs
- **Prompt Engineering**: If Kiro isn't understanding, try rephrasing or breaking down requests

---

## Next Steps & Resources

### Extend Your QR Code Portal

1. **Add QR Code Customization**:

   - Colors and gradients
   - Logo embedding
   - Custom shapes and patterns

2. **Implement Analytics**:

   - Track QR code scans
   - Geographic data
   - Scan statistics dashboard

3. **Add User Accounts**:

   - User registration and login
   - Save QR code history
   - Manage generated codes

4. **Bulk Operations**:
   - Generate multiple QR codes at once
   - Batch upload and decode
   - Export to various formats

### Learn More About Kiro

- **Advanced Agent Steering**: Create context-specific rules for different file types
- **Complex Agent Hooks**: Chain multiple hooks together
- **MCP Server Development**: Build custom MCP servers for your specific needs
- **Team Collaboration**: Share specs and steering docs across team members

### Related Technologies

- **FastAPI**: [https://fastapi.tiangolo.com/](https://fastapi.tiangolo.com/)
- **React**: [https://react.dev/](https://react.dev/)
- **TypeScript**: [https://www.typescriptlang.org/](https://www.typescriptlang.org/)
- **QR Code Libraries**:
  - Python: `qrcode`, `pyzbar`
  - JavaScript: `qrcode.react`, `html5-qrcode`

### Build More Projects

Try building other projects with Kiro:

- **REST API with Database**: Blog API with PostgreSQL
- **Real-time Chat App**: WebSocket-based chat with Redis
- **E-commerce Backend**: Product catalog with Stripe integration
- **Data Dashboard**: Analytics visualization with Chart.js

---

**Congratulations!** You've completed the Kiro tutorial. You now understand:

- Spec-driven development workflow
- Agent Steering for project-specific instructions
- Agent Hooks for automation
- Building full-stack applications with Kiro
- Testing and quality assurance strategies

Happy coding with Kiro!

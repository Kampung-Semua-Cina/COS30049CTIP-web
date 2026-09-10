# Smart Ground-Truthing & Digital Biodiversity System

### COS30049 Computing Technology Innovation Project

Web application for the Smart Ground-Truthing and Digital Biodiversity System developed for the COS30049 group project.

The web application provides the browser-based interface for conservation officers and administrators to manage biodiversity information, review field observations, monitor IoT data, and generate reports.

---

## Tech Stack

| Technology   | Purpose                           |
| ------------ | --------------------------------- |
| React        | Frontend UI                       |
| TypeScript   | Type-safe development             |
| Vite         | Development server and build tool |
| React Router | Page navigation                   |
| Supabase     | Backend services                  |
| PostgreSQL   | Relational database               |
| PostGIS      | Geographic/location data          |
| Git + GitHub | Version control and collaboration |
| ESLint       | Code quality                      |
| Prettier     | Code formatting                   |

> **Important:** Do not use Create React App for this project. React has deprecated Create React App for new applications. This project uses React + Vite + TypeScript.

---

# 1. Prerequisites

Before starting, install the following:

### Required

* [Node.js](https://nodejs.org/)
* [Git](https://git-scm.com/)
* [Visual Studio Code](https://code.visualstudio.com/)
* A modern web browser such as Google Chrome

### Recommended VS Code Extensions

Install these extensions:

1. **ES7+ React/Redux/React-Native Snippets**
2. **ESLint**
3. **Prettier - Code formatter**
4. **GitLens**
5. **Error Lens**
6. **GitHub Pull Requests and Issues**

React also provides React Developer Tools for inspecting React components, props and state.

---

# 2. Check Your Installation

Open a terminal in VS Code:

**Terminal → New Terminal**

Run:

```bash
node --version
```

and:

```bash
npm --version
```

Your Node.js version should satisfy the current Vite requirement:

```text
Node.js 20.19+ or 22.12+
```

Vite currently requires Node.js 20.19+ or 22.12+.

You can also check Git:

```bash
git --version
```

Example:

```text
node v22.x.x
npm 10.x.x
git version 2.x.x
```

If Node.js is too old, update Node.js before continuing.

---

# 3. Clone the Repository

Do **not** create a new React project if the repository already exists.

Clone the existing project instead.

```bash
git clone <GITHUB_REPOSITORY_URL>
```

For example:

```bash
git clone https://github.com/OUR-ORGANISATION/biodiversity-web.git
```

Then enter the project:

```bash
cd biodiversity-web
```

Open it in VS Code:

```bash
code .
```

---

# 4. Install Dependencies

After cloning the repository, install all project dependencies:

```bash
npm install
```

This reads `package.json` and installs the required dependencies into `node_modules`.

### Important

Do **not** commit `node_modules` to GitHub.

It is already excluded through `.gitignore`.

---

# 5. Set Up Environment Variables

Some parts of the application require environment variables.

Create a local environment file:

```text
.env.local
```

Use `.env.example` as the template.

Example:

```text
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

Your actual values will be provided through the team's agreed development setup.

### Important Security Rule

**Never commit `.env.local` to GitHub.**

Do not put:

* passwords
* private keys
* service-role keys
* database passwords
* API secrets

into source code or Git commits.

Only variables intended for the browser/client application should use the `VITE_` prefix.

---

# 6. Start the Development Server

Run:

```bash
npm run dev
```

Vite will display a local development URL, normally something similar to:

```text
http://localhost:5173/
```

Open the URL in your browser.

You should now see the Smart Ground-Truthing web application.

Vite provides the development server and supports the React + TypeScript project template used by this repository.

---

# 7. Available Commands

The main commands you will use are:

### Start development server

```bash
npm run dev
```

### Build the application

```bash
npm run build
```

### Preview the production build

```bash
npm run preview
```

### Run linting

```bash
npm run lint
```

### Format files

```bash
npm run format
```

> The exact commands available may change as the project develops. Check `package.json` for the authoritative list of scripts.

Vite's standard setup includes development, production build and preview workflows.

---

# 8. Project Structure

The web project is organised by responsibility rather than putting everything into `App.tsx`.

```text
biodiversity-web/
│
├── public/
│
├── src/
│   │
│   ├── assets/
│   │
│   ├── components/
│   │   ├── common/
│   │   ├── layout/
│   │   ├── plants/
│   │   ├── observations/
│   │   ├── maps/
│   │   ├── iot/
│   │   └── reports/
│   │
│   ├── pages/
│   │   ├── Login/
│   │   ├── Dashboard/
│   │   ├── Plants/
│   │   ├── Observations/
│   │   ├── Monitoring/
│   │   └── Reports/
│   │
│   ├── services/
│   │
│   ├── hooks/
│   │
│   ├── types/
│   │
│   ├── utils/
│   │
│   ├── App.tsx
│   ├── main.tsx
│   └── index.css
│
├── .env.example
├── .gitignore
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

The structure may evolve as the project grows. Changes to the architecture should be discussed with the team before making large structural changes.

---

# 9. Basic Development Workflow

Before starting work:

```bash
git pull
```

Create a new branch for your task.

Example:

```bash
git checkout -b feature/plant-management
```

Work on your changes.

Then check what changed:

```bash
git status
```

Add your files:

```bash
git add .
```

Create a meaningful commit:

```bash
git commit -m "feat: add plant management page"
```

Push your branch:

```bash
git push -u origin feature/plant-management
```

Then create a **Pull Request** on GitHub.

---

# 10. Branch Naming

Use descriptive branch names.

### Features

```text
feature/qr-scanner
feature/plant-management
feature/observation-review
feature/species-map
feature/iot-dashboard
feature/reports
```

### Bug fixes

```text
fix/login-validation
fix/map-loading
fix/plant-form
```

### Documentation

```text
docs/setup
docs/architecture
docs/testing
```

Avoid branches such as:

```text
test
stuff
new
changes
final
final2
really-final
```

---

# 11. Commit Message Convention

Use clear commit messages.

### New feature

```bash
git commit -m "feat: add plant species search"
```

### Bug fix

```bash
git commit -m "fix: prevent duplicate observation submission"
```

### Testing

```bash
git commit -m "test: add plant form validation tests"
```

### Documentation

```bash
git commit -m "docs: update development setup"
```

### Refactoring

```bash
git commit -m "refactor: simplify plant service"
```

A good commit should describe **what changed**, not who changed it.

---

# 12. Pull Request Rules

Before opening a Pull Request:

```bash
npm run lint
npm run build
```

Make sure both complete successfully.

Your Pull Request should include:

### Description

Explain:

* What you changed
* Why you changed it
* What issue/task it addresses

### Testing

Explain how you tested it.

Example:

```text
Tested plant search using:
- Scientific name
- Common name
- Partial search terms
- Empty search
```

### Screenshots

For UI changes, include screenshots where useful.

---

# 13. Code Style

Please follow these rules:

### Use TypeScript

Prefer:

```tsx
interface Plant {
  id: string
  scientificName: string
  commonName: string
}
```

rather than leaving important project data as untyped objects.

### Use functional components

Example:

```tsx
function PlantCard() {
  return (
    <div>
      ...
    </div>
  )
}

export default PlantCard
```

### Keep components focused

Avoid creating a single component containing hundreds of lines.

Instead of:

```text
PlantPage.tsx
    800 lines
```

split it into:

```text
PlantPage
├── PlantHeader
├── PlantInformation
├── PlantPhotos
├── PlantLocation
└── ObservationHistory
```

### Don't duplicate logic

If multiple pages perform the same operation, consider moving the logic into:

```text
services/
hooks/
utils/
```

---

# 14. React Component Guidelines

Prefer reusable components.

For example:

```tsx
<PlantCard plant={plant} />
```

rather than creating separate copies of the same UI for different pages.

Use props to make components reusable.

Example:

```tsx
interface PlantCardProps {
  plant: Plant
  onSelect: (plant: Plant) => void
}
```

---

# 15. Database Access

The frontend should not contain raw database logic everywhere.

Avoid doing this throughout your components:

```tsx
const { data } = await supabase
  .from('plants')
  .select('*')
```

Instead, put database-related operations into services.

Example:

```text
src/
└── services/
    ├── plantService.ts
    ├── observationService.ts
    └── sensorService.ts
```

Then pages/components can call:

```tsx
const plants = await getPlants()
```

This makes the application easier to maintain and test.

---

# 16. Authentication and Authorisation

The system will eventually have different user roles.

Expected roles include:

```text
Visitor
Botanist
Conservation Officer
Administrator
```

Do not rely only on hiding buttons in the frontend to protect functionality.

Example:

```tsx
if (user.role === 'admin') {
  // show admin button
}
```

This is useful for the user interface, but actual access control must also be enforced by the backend/database security layer.

---

# 17. Never Commit Secrets

Do not commit:

```text
.env
.env.local
```

Do not put secrets in:

```text
.tsx
.ts
.json
README.md
```

Do not commit:

```text
API passwords
Database passwords
Private API keys
Service-role keys
Access tokens
```

When in doubt, ask the team lead before committing something that may contain credentials.

---

# 18. Common Problems

## `npm` is not recognised

Node.js is probably not installed correctly or is not available in your PATH.

Check:

```bash
node --version
```

Restart VS Code after installing Node.js.

---

## `npm install` fails

First make sure you are inside the repository:

```bash
cd biodiversity-web
```

Then try:

```bash
npm install
```

If the team has recently changed dependencies, make sure you have pulled the latest changes:

```bash
git pull
npm install
```

---

## Port 5173 is already in use

Vite may automatically select another available port.

For example:

```text
http://localhost:5174/
```

Use the URL shown in the terminal.

---

## The application works for someone else but not me

First try:

```bash
git pull
npm install
npm run dev
```

If problems remain, check:

```bash
node --version
npm --version
```

and compare your environment with the other team member.

---

# 19. Before You Start Coding

Every developer should verify:

```text
[ ] Node.js installed
[ ] npm working
[ ] Git working
[ ] VS Code installed
[ ] Required extensions installed
[ ] Repository cloned
[ ] npm install completed
[ ] .env.local configured
[ ] npm run dev works
[ ] Application opens in browser
[ ] npm run lint works
[ ] npm run build works
```

Once all of these work, your environment is ready.

---

# 20. Important Project Rules

### 1. Don't work directly on `main`

Create a feature branch.

### 2. Pull before starting work

```bash
git pull
```

### 3. Keep commits focused

A commit should represent one logical change.

### 4. Test before creating a Pull Request

At minimum:

```bash
npm run lint
npm run build
```

### 5. Ask before changing shared architecture

Discuss major changes to:

* database structure
* authentication
* routing
* project structure
* shared components
* dependencies

with the team.

### 6. Keep the application working

Don't merge unfinished features into `main`.

---

# 21. Quick Start

For experienced teammates, the setup is simply:

```bash
git clone <GITHUB_REPOSITORY_URL>

cd biodiversity-web

npm install

# Create .env.local using .env.example

npm run dev
```

Then open the URL shown by Vite.

---

# 22. Useful Resources

### React

https://react.dev/

### Vite

https://vite.dev/

### TypeScript

https://www.typescriptlang.org/

### React Developer Tools

https://react.dev/learn/react-developer-tools

### Supabase

https://supabase.com/docs

### Git

https://git-scm.com/doc

---

## Project

**COS30049 Computing Technology Innovation Project**

**Smart Ground-Truthing and Digital Biodiversity System for Plant Species Documentation**

Industry Partner:

**NeuonAI (Sarawak Forestry Corporation's commercialisation partner)**

# DevOps Project 01: CI/CD Pipeline with Node.js & GitHub Actions

## 📖 Project Description

This project is the first in a series of DevOps practical labs. It demonstrates a simple Node.js API with an interactive web-based frontend, integrated with a **Production-Grade Continuous Integration (CI) Pipeline** using GitHub Actions.

The goal of this project is to showcase how to automate code quality checks (linting), run automated tests, and generate code coverage reports every time code is pushed. This ensures broken code is detected before it can be merged into the `main` branch.

## 🛠️ Tech Stack

- **Backend:** Node.js, Express.js
- **Frontend:** HTML, Vanilla JavaScript
- **Testing:** Node.js `assert`, `supertest`
- **Code Coverage:** `nyc` (Istanbul)
- **Linting:** ESLint
- **CI/CD:** GitHub Actions

---

## 📂 Project Directory Structure

```text
devops-project-01-ci-cd-pipeline/
│
├── .github/
│   └── workflows/
│       └── ci.yml              # Advanced GitHub Actions CI configuration
│
├── public/
│   └── index.html              # Frontend UI and API fetch logic
│
├── src/
│   └── server.js               # Express server and API endpoints
│
├── test/
│   └── test.js                 # Automated API tests using supertest
│
├── .eslintrc.json              # ESLint rules configuration
├── .eslintignore               # Folders for ESLint to ignore
├── package.json                # Project dependencies and scripts
└── README.md                   # Project documentation
```

---

## 🚀 How to Run Locally (Commands & Outputs)

### Prerequisites

Before starting, make sure you have installed:

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [Git](https://git-scm.com/)
- npm (included with Node.js)

### Step-by-Step Setup

### 1. Clone the Repository

```bash
git clone https://github.com/rajanshah23/devops-project-01-ci-cd-pipeline.git

cd devops-project-01-ci-cd-pipeline
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Start the Application

```bash
npm start
```

**Expected Output:**

```text
Server running on http://localhost:3000
```

Open your browser and navigate to:

```text
http://localhost:3000
```

You will see a UI where you can enter your name and trigger the API.

Try entering `error` to see how the frontend handles a `500 Internal Server Error`.

### 4. Run Automated Tests with Coverage

```bash
npm test
```

**Expected Output:**

```text
Running API Tests...

✅ Test 1 Passed: Successful API call
✅ Test 2 Passed: Default Guest behavior
✅ Test 3 Passed: Handled server error correctly

----------|---------|----------|---------|---------|-------------------
File      | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s
----------|---------|----------|---------|---------|-------------------
All files |      80 |    83.33 |      50 |   85.71 |
index.js  |      80 |    83.33 |      50 |   85.71 | 23-24
----------|---------|----------|---------|---------|-------------------
```

*Note: The coverage values above are illustrative expected output. Actual results depend on your implementation.*

### 5. Run the Linter

```bash
npm run lint
```

**Expected Output:**

If there are no linting errors, ESLint returns no output (silent success).

If an error exists, ESLint displays the exact file and line number where the issue occurred.

---

## ⚙️ How the Advanced CI Pipeline Works

The GitHub Actions workflow (`.github/workflows/ci.yml`) triggers on pushes and pull requests targeting the `main` branch.

To optimize execution speed and enforce code quality, the pipeline is split into **two parallel jobs**.

### Job 1: Lint

1. Checks out the source code using `actions/checkout`.
2. Sets up Node.js (v18).
3. Caches npm dependencies to speed up future workflow runs.
4. Runs `npm ci` for deterministic dependency installation.
5. Runs ESLint to identify syntax and code-quality issues.

### Job 2: Build & Test

1. Checks out the source code.
2. Sets up Node.js (v18) with npm dependency caching.
3. Runs `npm ci`.
4. Executes the automated test suite using `npm test`.
5. Generates a code coverage report.
6. Uploads the HTML coverage report as a GitHub Actions artifact so developers can download and review the tested and untested lines of code.

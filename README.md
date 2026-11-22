# DevOps Project 01: CI/CD Pipeline with Node.js & GitHub Actions

![CI Pipeline](https://github.com/rajanshah23/devops-project-01-ci-cd-pipeline/actions/workflows/ci.yml/badge.svg)

## 📖 Project Description

This project is the first in a series of DevOps practical labs. It demonstrates a simple Node.js API with an interactive web-based frontend, integrated with a complete **Continuous Integration (CI)** pipeline using GitHub Actions.

The goal of this project is to showcase how to automate the testing of an application every time code is pushed to a repository, ensuring broken code is never merged into the `main` branch.

## 🛠️ Tech Stack

- **Backend:** Node.js, Express.js
- **Frontend:** HTML, Vanilla JavaScript
- **Testing:** Node.js `assert`, `supertest`
- **CI/CD:** GitHub Actions

---

## 📂 Project Directory Structure

```text
devops-project-01-ci-cd-pipeline/
├── .github/
│   └── workflows/
│       └── ci.yml          # GitHub Actions CI configuration
├── public/
│   └── index.html          # Frontend UI and API fetch logic
├── src/
│   └── server.js           # Express server and API endpoints
├── test/
│   └── test.js             # Automated API tests using supertest
├── package.json            # Project dependencies and scripts
└── README.md               # Project documentation
```

---

## 🚀 How to Run Locally

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- Git
- npm (included with Node.js)

### Step-by-Step Setup

**1. Clone the repository**

```bash
git clone https://github.com/rajanshah23/devops-project-01-ci-cd-pipeline.git

cd devops-project-01-ci-cd-pipeline
```

**2. Install dependencies**

```bash
npm install
```

**3. Start the application**

```bash
npm start
```

Open your browser and navigate to:

```text
http://localhost:3000
```

You will see a UI where you can enter your name and trigger the API.

Try entering `error` to see how the frontend handles a `500 Internal Server Error`.

**4. Run automated tests**

```bash
npm test
```

This will run the `supertest` suite against the Express application and output the test results in your terminal.

---

## ⚙️ CI Pipeline

GitHub Actions automatically executes the CI workflow when:

- Code is pushed to the `main` branch.
- A pull request is created targeting the `main` branch.

The pipeline performs the following tasks:

1. Checks out the source code.
2. Sets up the Node.js environment.
3. Installs project dependencies.
4. Runs automated tests.
5. Reports the pipeline status on GitHub Actions.

---

## 🎯 Learning Objectives

By completing this project, you will understand:

- Basic Node.js application structure.
- REST API development using Express.js.
- Automated API testing with Supertest.
- Git and GitHub repository management.
- GitHub Actions workflow configuration.
- Continuous Integration fundamentals.
- Automated testing during code pushes and pull requests.

---

## 📊 Expected Outcome

After successfully configuring the GitHub Actions workflow, every push or pull request targeting `main` will automatically trigger the CI pipeline.

<text> </text>

A successful workflow indicates that the application dependencies were installed and the automated tests passed.

---

## 👨‍💻 Author

**DevOps Learning Lab – Project 01**

Part of a hands-on DevOps project series focused on learning industry-standard tools and technologies through practical implementation.


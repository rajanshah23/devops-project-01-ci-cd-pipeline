# DevOps Project 01: Simple CI/CD Pipeline

## Overview
A basic Node.js API with a frontend interface, designed to demonstrate a complete Continuous Integration (CI) workflow using GitHub Actions.

## Tech Stack
*   **Backend:** Node.js, Express
*   **Frontend:** HTML, Vanilla JS
*   **Testing:** Node Assert, Supertest
*   **CI/CD:** GitHub Actions

## How it works
Every push to the `main` branch triggers the GitHub Actions pipeline to install dependencies and run automated API tests. If tests fail, the pipeline fails.

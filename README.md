# Jenkins Demo App

A small Express.js application used to demonstrate a Jenkins CI pipeline and Docker image build.

When you open the app in a browser, it displays:

> Hello from Elevate Lab Task 1! My CI/CD pipeline works!

## Technology

- Node.js 18
- Express 4
- Docker
- Jenkins

## Run locally

Install dependencies and start the server:

```bash
npm install
npm start
```

Then visit [http://localhost:3000](http://localhost:3000).

## Run with Docker

Build the image and start a container:

```bash
docker build -t jenkins-demo-app .
docker run --rm -p 3000:3000 jenkins-demo-app
```

Open [http://localhost:3000](http://localhost:3000) to view the app.

## Jenkins pipeline

The `Jenkinsfile` defines these stages:

1. **Checkout Code** — checks out the repository using Jenkins SCM configuration.
2. **Install & Test** — runs `npm install` and `npm test`.
3. **Build Docker Image** — builds an image tagged `jenkins-demo-app`.

The pipeline uses Windows `bat` steps, so it expects to run on a Windows Jenkins agent with Node.js/npm and Docker installed and available on `PATH`. The current `npm test` script is a placeholder that prints a success message; it does not run a test suite.

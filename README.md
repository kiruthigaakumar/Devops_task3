task-3 Node.js App

This is a simple Node.js application that serves a "Hello from xops CI/CD" message. The project includes a GitHub Actions workflow for automated deployment to an EC2 instance.

 Project Structure

- `node_app/server.js` - Main server file using Node.js HTTP module.
- `node_app/package.json` - Project metadata and dependencies.
- `.github/workflows/deploy.yml` - GitHub Actions workflow for CI/CD deployment.

Getting Started

 Prerequisites

- Node.js (v22 or later recommended)
- npm

Installation

1. Clone the repository:
    ```sh
    git clone <your-repo-url>
    cd task-3/node_app
    ```

2. Install dependencies:
    ```sh
    npm install
    ```

Running Locally

Start the server:
```sh
npm start
```
Visit [http://localhost:3000](http://localhost:3000) in your browser.

Deployment

Deployment is automated using GitHub Actions. On every push to the `main` branch, the workflow in [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) will:

- SSH into your EC2 instance
- Sync project files
- Install dependencies
- Restart the app using PM2
Secrets Required

Set the following secrets in your GitHub repository:

- `SSH_PRIVATE_KEY` - Your EC2 SSH private key
- `SSH_USERNAME` - EC2 username (e.g., `ec2-user`)
- `EC2_PUBLIC_IP` - Public IP of your EC2 instance

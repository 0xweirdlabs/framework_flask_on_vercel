# Flask on Vercel

A minimal Flask application deployed on [Vercel](https://vercel.com/). This repository demonstrates how to run a Python/Flask backend seamlessly within Vercel’s Serverless Functions.

## Table of Contents

- [Overview](#overview)  
- [Features](#features)  
- [Getting Started](#getting-started)  
  - [Prerequisites](#prerequisites)  
  - [Installation](#installation)  
  - [Running Locally](#running-locally)  
- [Deployment to Vercel](#deployment-to-vercel)  
- [Project Structure](#project-structure)  
- [License](#license)  

---

## Overview

This project sets up a basic Flask application and shows how you can deploy it on Vercel’s platform without needing a dedicated server or external container orchestration. Once deployed, Vercel will automatically handle incoming HTTP requests through its serverless functions, routing them to the Flask application.

## Features

- **Minimal Setup**: Only the essential files needed to run a Flask app on Vercel.  
- **Serverless Deployment**: Vercel manages the infrastructure, removing the need for manual scaling or server management.  
- **Fast Development**: Quickly clone, install, and run locally before deploying with a simple command.  

---

## Getting Started

### Prerequisites

1. **Python 3.7+** (make sure you have a recent version of Python installed on your system)  
2. **Pipenv** or **pip** (depending on your preferred Python environment manager)  
3. (Optional) **Vercel CLI** if you want to deploy from your command line  

### Installation

1. **Clone this repository**:
   ```bash
   git clone https://github.com/0xweirdlabs/framework_flask_on_vercel.git
   cd framework_flask_on_vercel
   ```
2. **Create a virtual environment (if you’re using pipenv):**

   ```bash
   pipenv shell
   ```
   or using venv my prefured choise:

   ```bash
   python -m venv venv
   source venv/bin/activate   # Linux/Mac
   # .\venv\Scripts\activate  # Windows
   ```
3. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```
   (If you’re using Pipenv, run pipenv install instead.)


## Running Locally
To run the app locally, simply run:

```bash
python app.py
```

This will start the Flask development server at http://127.0.0.1:5000, or whichever port is configured in your code. You can then open that URL in your browser to see the application in action.

## Deployment to Vercel
There are two common ways to deploy this project to Vercel:

1.  **Through Git Integration**:
  - Create a new Vercel project and link it to your GitHub repository (or another supported repo host).
  - Every push to the main (or configured) branch will automatically trigger a deployment.

2.  **Through Git Integration**:  
  - Install the Vercel CLI globally:
    ```bash
    npm install -g vercel
    ```
  - Log in to your Vercel account:  
    ```bash
    vercel login
    ```
  - From the project root, run: 
    ```bash
    vercel
    ```
  - Follow the prompts to configure and deploy your project.  

#### Configuration Files

- vercel.json:
  This file tells Vercel how to build and serve your Flask app. Typically, it includes:
  ```json
  {
  "builds": [
    { "src": "app.py", "use": "@vercel/python" }
  ],
  "routes": [
    { "src": "/(.*)", "dest": "app.py" }
  ]
  }
  ```

## License
This project is open-source under the MIT License. Feel free to use it, modify it, and distribute it in your projects.

Have fun!!




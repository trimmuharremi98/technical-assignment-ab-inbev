Explanation of the Dockerfile Steps

Base Image:
    -Uses the official Node.js 18 Alpine image for a lightweight and secure environment.

Working Directory:
    -Sets /usr/src/app as the working directory for all subsequent instructions.

Dependency Installation:
    -Copies package.json and package-lock.json to the container and installs dependencies using npm install.

Source Code:
    -Copies the application source code into the container.

TypeScript Compilation:
    -Compiles TypeScript to JavaScript, if applicable, using npm run build.

Port Exposure:
    -Exposes port 3000 to allow external access to the application.

Startup Command:
    -Command to start the application using npm start.
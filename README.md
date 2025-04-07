Day 1:Docker and Kubernetes
# Day 1: Introduction to Docker and Image Creation Using Application

## Trainer's Instructions

Today in the session, our trainer explained the following:

- Introduction to Docker and containerization
- How Docker helps in application deployment and environment consistency
- Hands-on demo: building a Docker image using an application in Visual Studio Code
- Explanation of Docker CLI commands:
  - `docker build`
  - `docker run`
  - `docker ps`
  - `docker images`
  - `docker logs`
- Task given:
  - Create a simple application (example: Sorting Visualizer)
  - Write a Dockerfile
  - Build a Docker image
  - Run the container and verify it

## What I Learned

### Docker Fundamentals

- Understood Docker concepts: images, containers, layers
- Learned to use Docker CLI commands for managing containers and images
- Learned how to write a Dockerfile from scratch
- Understood port mapping and the need for using `host='0.0.0.0'` in Flask
- Debugging using `docker logs`
- Learned about exit codes and what `Exited (0)` and `Exited (1)` mean

### Visual Studio Code Usage

- Created a new project in VS Code
- Wrote a basic Flask application
- Created `requirements.txt` and `Dockerfile`
- Built Docker image using the terminal in VS Code
- Solved issues related to container not showing port and exiting unexpectedly

## What I Developed

### Project: Sorting Visualizer

A simple Flask-based web app that displays a basic sorting visualizer message. The application is containerized using Docker.

**Project Structure:**

SortingVisualizer/ ├── app.py ├── Dockerfile ├── requirements.txt └── README.md


**Dockerfile:**

```dockerfile
FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

CMD ["python", "app.py"]

Steps to Build and Run:

docker build -t sorting-visualizer:latest .
docker run -d -p 5000:5000 sorting-visualizer:latest

Outcome

    Successfully created and ran a Docker image from the application
    ![Screenshot 2025-04-08 at 00-22-58 Sorting Visualizer](https://github.com/user-attachments/assets/d2cab024-44c4-40b9-a30c-ed7f6686dcb3)



    Application runs on localhost and displays the expected page

    Task for Day 1 is completed and pushed to GitHub

    Learned the overall Docker workflow from build to run

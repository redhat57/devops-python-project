# devops-python-project
**Step 1: Build the Docker Image**

Navigate to the directory containing the Dockerfile and app.py file and build the Docker image using the docker build command. Give your image a name (e.g., my-python-app-image):

`$ docker build -t my-python-app-image .`
The -t flag specifies a tag (name) for your image, and the . at the end specifies the build context (current directory).

**Step 2: Run the Docker Container**

Once the image is built, you can run a Docker container from it using the docker run command. Map port 8099 on the host to port 8099 in the container:

`$ docker run -d -p 8099:8099 my-python-app-image`
The -d flag runs the container in detached mode (in the background).
The -p flag maps port 8099 on your host to port 8099 in the container.

**Step 3: Access the Python Application**
You can access the Python application by opening a web browser or using a tool like curl to visit http://localhost:8099. You should see the "Hello, Docker!" message served by your Python web application.

Dockerfile:
==========================================================
1. Uses the official Python 3.8 image as the base image.
2. Sets the working directory inside the container to /app.
3. Copies the contents of the current directory (including app.py) into the container's /app directory.
4. Exposes port 8099 for the application.
5. Specifies the command to run the Python application.
==========================================================

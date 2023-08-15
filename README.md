

# CI/CD for a Simple Web Application


## We have forked a webapp: https://github.com/mmumshad/simple-webapp-flask
  This is a simple web application using [Python Flask](http://flask.pocoo.org/) and [MySQL](https://www.mysql.com/) database. 
   
## Dockerfile (Containerization) & Github Actions (CI/CD Workflow)
  
  I have written a simple Dockerfile for containerizing the webapp project and a basic GitHub Actions workflow configuration main.yml for creating a CI/CD pipeline.

  This is a basic setup for our CI/CD pipeline using GitHub Actions. It sets up the environment, installs dependencies, builds a Docker image, and then pushes the image to a Docker registry. We need to replace <our-image-name> with the actual name we want for our Docker image.
   
## Documentation on how to run and test containerized app locally and explaining CI workflow

  -- We need to make sure we have Docker installed on our local machine.
  -- Clone the GitHub repository.
  -- Navigate to the project directory and build the Docker image: docker build -t my-webapp .
  -- Run the container: docker run -p 80:80 my-webapp
  -- Access the web app in your browser at http://localhost:80

  This GitHub Actions workflow will build the Docker image, publish it to Docker Hub, and trigger whenever there's a push to the main branch. It ensures that our web app is containerized, tested, and deployed automatically.

## Additional points to consider

  We'll need to configure the secrets (DOCKER_USERNAME and DOCKER_PASSWORD) in our GitHub repository to allow the workflow to log in and push to your Docker registry. 

    
## Missing CD part:

  For the missing CD part (for which  don't have any avalable environment), if we are using AWS environment we can use any Compute Services namely ECS, EKS etc (I have commented the CD part inside main.yml) & Container Image Repo as ECR.

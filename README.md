# 🐳 Dockerized Website Deployment with NGINX

## Project Overview

This project demonstrates the complete process of containerizing a static website using Docker and NGINX, running it locally, verifying the website, creating a Docker image from the container, and publishing the final image to Docker Hub.

---

## 1. Clone the Project

The provided GitHub repository was cloned into the Ubuntu environment.

```bash
git clone https://github.com/MenaMagdyHalem/Course-Docker.git
cd Course-Docker/sample-website
```

![Clone Repository](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2019-53-25.png)

---

## 2. Create the Dockerfile

A Dockerfile was created inside the `sample-website` directory.

```dockerfile
FROM nginx:latest

COPY . /usr/share/nginx/html

EXPOSE 80
```

The Dockerfile uses NGINX as the base image, copies the website files into the default NGINX web root, and exposes port 80.

![Dockerfile and Build](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2020-00-25.png)

---

## 3. Build the Docker Image

The Docker image was built using:

```bash
docker build -t docker-project .
```

![Docker Build](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2020-00-25.png)

---

## 4. Run the Docker Container

The Docker image was used to create and run a container:

```bash
docker run -it -d -p 8080:80 --name my-container docker-project
```

The running container was verified using:

```bash
docker ps
```

### Port Mapping

`8080` on the host → `80` inside the container

![Docker Run](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2020-06-10.png)

---

## 5. Verify the Website

The website was accessed through:

```text
http://localhost:8080
```

The custom website was successfully served by NGINX from inside the Docker container.

![Website Verification](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2020-06-55.png)

---

## 6. Commit the Container

The running container was committed to create a new Docker image:

```bash
docker commit my-container my_website-image
```

![Docker Commit](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2020-18-46.png)

---

## 7. Tag the Docker Image

The image was tagged with the Docker Hub repository name:

```bash
docker tag my_website-image moatazdiaaata/my-website:v1
```

![Docker Tag](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2020-18-46.png)

---

## 8. Push the Image to Docker Hub

The tagged image was pushed to Docker Hub:

```bash
docker push moatazdiaaata/my-website:v1
```

![Docker Push](https://raw.githubusercontent.com/MoatazDiaaAta/Course-Docker/main/sample-website/screenshots/Screenshot%20From%202026-09-27%2020-18-55.png)

---

## 🐳 Docker Hub Repository

**Repository:** `moatazdiaaata/my-website`

**Image:** `moatazdiaaata/my-website:v1`

https://hub.docker.com/r/moatazdiaaata/my-website

---

## 🛠️ Technologies Used

- Docker
- Dockerfile
- NGINX
- Ubuntu
- Git
- GitHub
- Docker Hub
- HTML
- CSS
- JavaScript

---

## ✅ Final Result

The static website was successfully cloned, containerized using Docker and NGINX, built into a Docker image, run and verified locally, committed into a new image, tagged, and pushed successfully to Docker Hub.

All major project steps are documented above with their corresponding screenshots.

## 👨‍💻 GitHub Repository

https://github.com/MoatazDiaaAta/Course-Docker

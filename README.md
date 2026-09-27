# 🐳 Dockerized Website Deployment with NGINX

## Project Overview

This project demonstrates the complete process of containerizing a static website using Docker and NGINX, running it locally, verifying the website, creating a Docker image from the container, and publishing the final image to Docker Hub.

---

## 1. Clone the Project

The project was cloned from the provided GitHub repository into the Ubuntu environment.

```bash
git clone https://github.com/MenaMagdyHalem/Course-Docker.git
cd Course-Docker/sample-website

FROM nginx:latest

COPY . /usr/share/nginx/html

EXPOSE 80

docker build -t docker-project .

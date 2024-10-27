# 🤗 Hugging Face packaging using GitHub Container Registry

Learn how to create a container and package it with GitHub Actions. This repository gives you a good starting point for a Dockerfile, GitHub Actions workflow, and Python code.

The web application uses FastAPI with Hugging Face and exposes a single endpoint that you can interact with it. 

Fork this repository and run the GitHub Actions as-is so that you can register your own containerized application with no modifications needed.

# Run Steps:
## Locally
* To run locally, iniciate uvicorn server. Inside webapp folder run the following code to start the uvicorn server
```
cd webapp
uvicorn --host 0.0.0.0 main:app
```

* Open the link and one is presented with the HTMLResponse "A self-documenting API to interact with a GPT2 model and generate text"

* Going to path /docs one get to interact with the model through FastAPI

## Docker Container
* Check if Docker is installed with the following command (should return path of Docker instalation):
```
which docker
```

* Move to the directory where the Docker file is present

* Run following command to build Docker container:
```
docker build -t huggingface:local
```

* Run following command to run the application inside Docker container:
```
docker run -i -p 8000:8000 huggingface:local
```

* Interact with application through Swagger FastAPI
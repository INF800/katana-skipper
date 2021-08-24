# Katana ML Skipper
[![PyPI - Python](https://img.shields.io/badge/python-v3.7+-blue.svg)](https://github.com/katanaml/katana-skipper)
[![GitHub Stars](https://img.shields.io/github/stars/katanaml/katana-skipper.svg)](https://github.com/katanaml/katana-skipper/stargazers) 
[![GitHub Issues](https://img.shields.io/github/issues/katanaml/katana-skipper.svg)](https://github.com/katanaml/katana-skipper/issues) 
[![Current Version](https://img.shields.io/badge/version-21.1-green.svg)](https://github.com/katanaml/katana-skipper)

This is a simple and flexible ML workflow engine. It helps to orchestrate events across a set of microservices and create executable flow to handle requests. Engine is designed to be configurable with any microservises. Enjoy!

![Skipper](https://github.com/katanaml/katana-skipper/blob/master/skipper.png)

## Author

Katana ML, Andrej Baranovskij

## Instructions

### Start/Stop

#### Docker Compose

Start:

```
docker-compose up --build -d
```

Stop:

```
docker-compose down
```

This will start RabbitMQ container. To run engine and services, navigate to related folders and follow instructions.

Web API FastAPI endpoint:

```
http://127.0.0.1:8080/api/v1/skipper/tasks/docs
```

#### Kubernetes

Build Docker images:

```
docker-compose build
```

Setup Kubernetes services:

```
./kubectl-setup.sh
```

Remove Kubernetes services:

```
kubectl delete all --all -n katana-skipper
```

```
kubectl delete all -all -n rabbits
```

### Components

* **[api](https://github.com/katanaml/katana-skipper/tree/master/api)** - Web API implementation
* **[workflow](https://github.com/katanaml/katana-skipper/tree/master/workflow)** - workflow logic
* **[services](https://github.com/katanaml/katana-skipper/tree/master/services)** - a set of sample microservices, you should replace this with your own services. Update references in docker-compose.yml
* **[rabbitmq](https://github.com/katanaml/katana-skipper/tree/master/rabbitmq)** - service for RabbitMQ broker
* **[skipper-lib](https://github.com/katanaml/katana-skipper/tree/master/skipper-lib)** - reusable Python library to streamline event communication through RabbitMQ
* **[logger](https://github.com/katanaml/katana-skipper/tree/master/logger)** - logger service

### URLs

* Web API: http://127.0.0.1:8080/api/v1/skipper/tasks/docs
* RabbitMQ: http://localhost:15672/ (skipper/welcome1)
* PyPI: https://pypi.org/project/skipper-lib/

## Usage

You can use Skipper engine to run Web API, workflow and communicate with a group of ML microservises implemented under services package.

## License

Licensed under the Apache License, Version 2.0. Copyright 2020-2021 Katana ML, Andrej Baranovskij. [Copy of the license](https://github.com/katanaml/katana-pipeline/blob/master/LICENSE).

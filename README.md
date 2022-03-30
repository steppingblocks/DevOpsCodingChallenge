# Flask + Redis Devops Playground

This repository contains a practice flask app which connects to a Redis database. Your goal is to:
- make sure you can run the application locally
- build a docker file to run the application inside docker
- write a docker-compose.yml file in order to run the application along side with a redis container
- write corresponding kubernets pods, services and deployment file

## 1.Running the application locally

First cd to the flask folder, then make sure you have a local python environment >= 3.8, and install the required dependencies by running:
`pip install -r requirements.txt`

Make sure you install locally a copy of Redis, and run it initially in a separate shell:
`redis-server`

Then finally, you can get inside the flask folder and run:
`python run.py`

Once the application is up, you should be able to navigate to the localhost URL returned by your terminal to access the app. Alternatively you can visit:

`http://0.0.0.0:5000/?user=Bob`

to see the app in action. 

Your first assignment is to run the following commands and share with us the output:
```
curl http://0.0.0.0:5000/\?user\=Bob
curl http://0.0.0.0:5000/\?user\=bob
curl http://0.0.0.0:5000/\?user\=wolfe
curl http://0.0.0.0:5000/\?user\=rush
```

## 2.Build a docker container to run the app

Your next task is to write a Dockerfile which will allow the flask app above to be containerized. 

Make sure you place the resulting Dockerfile inside the flask folder.


## 3.Write a Docker Compose file to orchestrate locally

With the Dockerfile you built in the step above, you still need to run a local redis-server instance. Your goal for this task is to write a simple docker-complose.yml at the root of the project which will launch both the container you build in the previous step, as well as a redis container (we recommend using the image `redis:alpine`).


## 4.Write kubernetes config files for everything

Now, running the app in a containered fashion locally is awesome, but now we want to ship it to one of our K8 clusters, so we want you to write the following k8 config files so that it can be easily deployed:
- application pod file
- application service file
- appplication deployment file
- redis pod file
- redis servive file

Please place those files inside a k8_configs folder at the root of the project.

We encourage you to install minikube if you don't have it installed locally already to test your kubernetes config files.

Thank you in advance for your time and good luck!


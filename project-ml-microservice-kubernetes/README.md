[![CircleCI](https://circleci.com/gh/FahmyKhalilM/DevOps_Microservices.svg?style=svg)](https://circleci.com/gh/FahmyKhalilM/DevOps_Microservices)

##### Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

###### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

###### Setup the Environment

* Create a virtualenv and activate it
* python3 -m venv ~/.devops
* source ~/.devops/bin/activate
* Run `make install` to install the necessary dependencies


####### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps
Docker:
* install docker as described in the [link](https://docs.docker.com/engine/install/ubuntu/).
* * Run `./run_docker.sh`
*  * Run `docker ps` to check if docker is running.
 * Run `./make_prediction.sh` to make prediction and copy/paste the logging info at terminal to `output_txt_files/docker_out.txt`

minikube:
*  To install the latest minikube stable release on x86-64 Linux using binary download:
*  curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
*  sudo install minikube-linux-amd64 /usr/local/bin/minikube
*  minikube start
*  Run `kubectl get pods` to see which pods are running.
*  Run `./run_kubernetes.sh`
*  Run `./make_prediction.sh` to make prediction and copy/paste the logging info at terminal to `output_txt_files/kubernetes_out.txt`

kubectl
Download the latest release with the command of kubectl:
url -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
Then install 
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

Flask App:
* Run `./run_docker.sh` to build and start the Flask app container. 
* Run `./upload_docker.sh` to upload the container to docker hub.  

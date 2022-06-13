<img scr="circleci_success.PNG"/>

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

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

## Setup the Environment
*1.	If you haven't already done so, clone the project repository, and navigate to the project folder.
 	git clone https://github.com/udacity/DevOps_Microservices.git
	cd DevOps_Microservices/project-ml-microservice-kubernetes

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Installing dependencies via project Makefile. Many of the project dependencies are listed in the file requirements.txt; these can be installed using pip commands in the provided Makefile. While in your project directory, type the following command to install these dependencies.
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### un Lint Checks
This project also must pass two lint checks; hadolint checks the Dockerfile for errors and pylint checks the app.py source code for errors.
1.	Install hadolint following the instructions, on hadolint's page:
For Mac:
 brew install hadolint
2. For Windows:
 scoop install hadolint

### Kubernetes Steps

* Setup and Configure Docker locally
Docker
You will need to use Docker to build and upload a containerized application. If you already have this installed and created a docker account, you may skip this step.
1.	You’ll need to create a free docker account, where you’ll choose a unique username and link your email to a docker account. Your username is your unique docker ID.
2.	To install the latest version of docker, choose the Community Edition (CE) for your operating system, on docker’s installation site. It is also recommended that you install the latest, stable release:
3.	After installation, you can verify that you’ve successfully installed docker by printing its version in your terminal: docker --version

* Setup and Configure Kubernetes locally
Install Minikube
To run a Kubernetes cluster locally, for testing and project purposes, you need the Kubernetes package, Minikube. This operates in a virtual machine and so you'll need to download two things: A virtual machine (aka a hypervisor) then minikube. Thorough installation instructions can be found <a target="_blank" href="https://kubernetes.io/docs/tasks/tools/install-minikube/">here</a>. Here is how I installed minikube:
1.	Install VirtualBox:
For Mac:
brew cask install virtualbox
For Windows, I recommend using a <a target="_blank" href="https://www.virtualbox.org/wiki/Downloads">Windows host</a>.
2.	Install minikube:
For Mac:
brew cask install minikube
For Windows, I recommend using the <a target="_blank" href="https://kubernetes.io/docs/tasks/tools/install-minikube/">Windows installer</a>.

* Create Flask app in Container
* Run via kubectl

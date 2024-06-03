# This is a file that captures the reasoning behind the decisions in the IP

Base image(s) used: node.js:alpine was used to have the total image size as small as possible.

The declaratives used declare the directory to work with and the run commands to install node, and all packages listed in the package.json file. It then exposes the application on the designated port. 3000 for the client and 5000 for the backend

###### Screenshot of the client image

![Screenshot of the client image on Docker hub](/screenshots/client.png "Client image on Socker hub")

###### Screenshot of the backend image

![Screenshot of the backend image on Docker hub](/screenshots/backend.png "Client image on Socker hub")

## Ansible and Terraform

I am using vspehere instead of vagrant box as my computer is on the new silicon architecture macs.

# Kubernetes

I will be creating a cluster that has three nodes, two with one pod each to house the containers for backend and frontend, and one to act as the master.

Statefulsets: I am not utilizing stateful sets to set up a storage layer as my application connects to a mongoDB Atlas account and hence the data is saved to an external database and queried with the API at the /api/products endpoint

The MONGODB_URI is provided as an ENV variable at the point of installation. As this repo is public, this file is excluded in the .gitignore and .dockerignore files. An alternative here in a work environment would be to include the file in the docker deploy setup, or to have another setup to manage revolving access keys and include the database as one of them.

There are two service files to expose both the backend and client applications to external traffic.

All Kubernetes related files are in the kube folder to ensure proper file structure. They also do not have any local dependecies as the containers would get images from docker-hub.
# This is a file that captures the reasoning behind the decisions in the IP

Base image(s) used: node.js:alpine was used to have the total image size as small as possible.

The declaratives used declare the directory to work with and the run commands to install node, and all packages listed in the package.json file. It then exposes the application on the designated port. 3000 for the client and 5000 for the backend

###### Screenshot of the client image

![Screenshot of the client image on Docker hub](/screenshots/client.png "Client image on Socker hub")

###### Screenshot of the backend image

![Screenshot of the backend image on Docker hub](/screenshots/backend.png "Client image on Socker hub")
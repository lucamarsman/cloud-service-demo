Project Name: cloud-service-demo

Purpose: Demonstrating Version Control For A Cloud Project

Files Included: index.html, README.md, Dockerfile

Version control helps a cloud project by tracking changes to source code and configuration files. It allows a team to collaborate, revert mistakes, track bugs, and maintain a history of an application/project.


Docker is a contanerization technology that allows applications to be packaged/disributed/ran in their own isolated enviornments. 
A Docker image is a read-only collection that includes everything required to run an application (source code, runtime, dependencies/libraries, configurations).
A Docker container is a running instance of a Docker image which includes a writeable layer on top of the read-only layer, which allows the application to modify/create files without altering the original image.

How to build and run this application

	- Ensure docker is installed using "docker --version" as well as running using "docker info"
	- Clone the repository to your local machine using "git clone https://github.com/lucamarsman/cloud-service-demo.git"
	- Change to the cloned directory and run "docker build -t cloud-service-demo:1.0 ." to build the image
	- Run "docker run -d --name cloud-demo-container -p 8080:80 cloud-service-demo:1.0" to run the image in a container
	- In a browser navigate to localhost:8080 to view the running web application

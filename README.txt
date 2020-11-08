So, where does Docker come into play here? Remember, 
our idea was to have two containers: one for running 
the tests and the other for running Jenkins (we’ll see this later). 
Make sure that you have switched to Linux containers, 
OS/Arch: under Server: Docker Engine - Community in docker version 
should say linux/amd64. 

Build the dockerized Jenkins image using the below command:
1. >docker build -t jenkins-docker-image -f JenkinsDockerfile .

Run the container with the docker daemon mounted:
2. >docker run -d -p 8080:8080 --name jenkins-docker-container -v /var/run/docker.sock:/var/run/docker.sock jenkins-docker

Verify whether jenkins-docker-container is running with docker: 
3. >ps -a

4. Open http://localhost:8080/ in your browser to see the Unlock Jenkins page













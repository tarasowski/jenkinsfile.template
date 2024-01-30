# To get docker as node running follow these steps

1. Launch an ec2 machine (called node)
2. Install docker with ansible on the node [here](https://github.com/tarasowski/jenkinsfile.template/blob/main/jenkins-node-docker-playbook.yml)
3. Connect via ssh to the node and run sudo vi /lib/systemd/system/docker.service
4. Configure docker to listen on tcp port, find the line ExecStart and change it with `ExecStart=/usr/bin/dockerd -H unix:///var/run/docker.sock -H tcp://0.0.0.0:2375`
5. Restart docker daemon `sudo systemctl daemon-reload && sudo systemctl restart docker`
6. Check the status if the daemon is running with `sudo systemctl status docker`
7. Open the port in the security group `2375`
8. Go to Jenkins Configuration -> Clouds -> Install docker plugin
9. Give a name to the docker cloud, please don't use whitespaces instead _ underscore
10. Add the docker host: `tcp://<your-ec2-ip>:2375`
11. Add ssh credentials and click on test connection
12. Tick the box enabled
13. Click add docker template and fill in the details for the Docker images you want to use as agents.
14. Add a label for this agent template (you'll use this in your Jenkins jobs to specify that they should run on this Docker agent)
15. Add the docker image to use for this agent. This image should have all the tools your Jenkins jobs need to run. (you can use it later to restric the jobs to a specific label). `Note: there needs to be a specific image settings at least java installed to run jenkins, you can't use only python:3.11 or something similar` -> you can start with this image: `devopsjourney1/myjenkinsagents:python`

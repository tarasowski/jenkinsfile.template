Setting up Jenkins

1. Install jenkins via ansible playbook on ec2 from ansible master
2. Create a freestyle job to print out hello world from main.py
3. Create a webhook to trigger actions github -> jenkins -> start build
4. Change the main.py -> push to github -> start the build
5. Configure agents (cloud agents) -> docker (docker-agent-python)
6. Configure cloud docker -> [here](https://github.com/tarasowski/jenkinsfile.template/blob/main/docker-clouds.md)
7. Pick an image that can run your script main.py in the docker container
    a. it should be able to run your python main.py script
9. Choose the newly created agent to run the job (docker-container-name)
    a. restrict where this project can be run
10. Run build now to run the build on the newly created docker agent

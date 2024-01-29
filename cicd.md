# Setting up CI/CD using groovy

0. Create a small python project (up to your choice)
    1. should be inside a myapp folder
    2. it should be able get some cli arguments
    3. it should return a reponse
    4. it should have at least 1-3 pip packages
    5. they should be installed during the build step
    6. it should have a test file that can be run later in the pipeline
2. Create a pipeline project
3. It should run in the newly created docker agent
4. Use jenkinsfile.template to crate a jenkinsfile https://github.com/tarasowski/jenkinsfile.template/blob/main/jenkinsfile.template
    5. Change agent node in the template to "docker-agent-python"
6. Use triggers to periodically (every minute) pull the code from github or try to setup webhooks for github
7. Use pipeline script from SCM -> github repository
8. Let jenkins install the python dependencies in the build step
9. Run a test (write a test for your python script) in the test phase
10. On the deploy step simply run the python script

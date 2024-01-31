# The last missing step in the ci/cd process 🚀

1. Create a simple flask server `GET /health -> reponse {"message": "I'm super good"}`
2. Create a test for the flask server to test the single GET endpoint
3. Commit the app to github (can be either containerized or not, doesn't matter)
4. Build a pipeline to get the source code from github, run a test and deploy to another ec2 machine which acts as a server

## Some ideas 🎉
- First take 5 to 10 minutes and present your approach
- Develop the application
- In deploy step should be able to run the deployment via ansible, it should pick up the app and deploy to the server
- SSH key for the server can be stored in Jenkins Credentials and referenced via env variables --private-key

```
/my-flask-app
|-- app.py
|-- test_app.py
|-- deploy.yml
|-- inventory.ini
|-- Jenkinsfile
```
  
## Bonus 🎁
- If you have time include monitoring loki/grafana or prometheus/grafana

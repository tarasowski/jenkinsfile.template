# The last missing step in the ci/cd process 🚀

1. Create a simple flask server `GET /health -> reponse {"message": "I'm super good"}`
2. Create a test for the flask server to test the single GET endpoint
3. Commit the app to github (can be either containerized or not, doesn't matter)
4. Build a pipeline to get the source code from github, run a test and deploy to another ec2 machine which acts as a server

## Approach 🎉
- First take 5 to 10 minutes and present your approach
- Develop the application
- Start with the server configuration (write a playbook) + configure the server
- Once server is configured and it's capable of running the flask server app, start building out the pipeline

## Some ideas 💡
- Use ansible playbook to configure the server machine from ansible master
- Make sure the server machine can run python e.g. nginx as reverse proxy
- In deploy step should be able to run the deployment via ansible, it should pick up the app and deploy to the server

## Bonus 🎁
- If you have time include monitoring loki/grafana or prometheus/grafana

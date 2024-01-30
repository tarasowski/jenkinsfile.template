# To get docker as node running follow these steps

1. Launch an ec2 machine (called node)
2. Install docker with ansible on the node [here](https://github.com/tarasowski/jenkinsfile.template/blob/main/jenkins-node-docker-playbook.yml)
3. Connect via ssh to the node and run sudo vi /lib/systemd/system/docker.service
4. Configure docker to listen on tcp port, find the line ExecStart and change it with `ExecStart=/usr/bin/dockerd -H unix:///var/run/docker.sock -H tcp://0.0.0.0:2375`

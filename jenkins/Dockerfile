FROM jenkins/jenkins:lts

USER root

# Install docker + kubectl
RUN apt-get update && \
    apt-get install -y docker.io curl && \
    curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl && \
    chmod +x kubectl && \
    mv kubectl /usr/local/bin/

# Allow jenkins user to use docker
RUN usermod -aG docker jenkins

USER jenkins


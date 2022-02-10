FROM centos:7

# update system & install basics
RUN yum update -y
RUN yum install -y git curl jq unzip wget

# install JDK-11
RUN yum install -y java-11-openjdk-devel

# install Maven
RUN yum install -y maven

# Install AWS CLI
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN ./aws/install

# Install Kubectl
RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.22.0/bin/linux/amd64/kubectl
RUN chmod +x ./kubectl
RUN mv ./kubectl /usr/local/bin/kubectl

# Install Terraform
RUN yum-config-manager --add-repo http://rpm.releases.hashicorp.com/RHEL/hashicorp.repo
RUN yum -y install terraform

# Install Helm Charts
RUN wget https://get.helm.sh/helm-v3.6.3-linux-386.tar.gz
RUN tar -zxvf helm-v3.6.3-linux-386.tar.gz
RUN mv linux-386/helm /usr/local/bin/helm
RUN rm helm-v3.6.3-linux-386.tar.gz

# Install Docker to build Docker images
RUN yum install -y yum-utils
RUN yum-config-manager --add-repo  https://download.docker.com/linux/centos/docker-ce.repo
RUN yum install -y docker-ce docker-ce-cli containerd.io







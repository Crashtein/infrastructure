FROM jenkins/ssh-agent:5.12.0-jdk17
ENV DEBIAN_FRONTEND="noniteractive"
RUN apt update && apt install -y curl python3 python3-pip unzip ansible git
RUN groupadd -g 997 docker && usermod -aG docker jenkins
RUN curl -fsSL https://get.docker.com | bash
RUN curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN ./aws/install --bin-dir /usr/local/bin --install-dir /usr/local/aws-cli --update
RUN rm awscliv2.zip && rm -R ./aws

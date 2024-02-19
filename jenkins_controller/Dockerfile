FROM jenkins/jenkins:2.414.2-lts-jdk17
ENV JAVA_OPTS='-Djenkins.install.runSetupWizard=false'
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
# RUN curl -s https://raw.githubusercontent.com/Panda-Academy-Core-2-0/Infrastructure/main/jenkins_controller/plugins.txt > /usr/share/jenkins/ref/plugins.txt
USER root
RUN apt-get update && apt-get install -y python3 python3-pip
USER jenkins
RUN jenkins-plugin-cli --plugins -f /usr/share/jenkins/ref/plugins.txt

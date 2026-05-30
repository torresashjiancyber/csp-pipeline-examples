FROM alpine:3.20

#Create Ant Dir
RUN mkdir -p /opt/ant/
#Download And 1.9.8
RUN wget http://archive.apache.org/dist/ant/binaries/apache-ant-1.9.8-bin.tar.gz -P /opt/ant
#Unpack Ant
RUN tar -xvzf /opt/ant/apache-ant-1.9.8-bin.tar.gz -C /opt/ant/
# Remove tar file
RUN rm -f /opt/ant/apache-ant-1.9.8-bin.tar.gz
# Note: sonar-ant-task 2.3 removed - abandoned since 2014
# For SonarQube integration, use sonar-scanner-cli or SonarQube Gradle/Maven plugins instead
#Install JDK 1.8
RUN apk --update add openjdk8
#Install GIT
RUN apk --update add git
#Install Curl
RUN apk --update add curl
#Setting Ant Home
ENV ANT_HOME=/opt/ant/apache-ant-1.9.8
#Setting Ant Params
ENV ANT_OPTS="-Xms256M -Xmx512M"
#Updating Path
ENV PATH="${PATH}:${HOME}/bin:${ANT_HOME}/bin"

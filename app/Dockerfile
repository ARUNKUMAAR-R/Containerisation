FROM openjdk:11 as MAVEN-BUILD
RUN apt update && apt install maven -y && apt install git -y
WORKDIR /usr/src/app/
RUN git clone https://github.com/ARUNKUMAAR-R/Containerisation.git
RUN cd ./vprofile-project && mvn install -DskipTests 


FROM tomcat:9-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=MAVEN-BUILD /usr/src/app/vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
ENTRYPOINT ["catalina.sh","run"]


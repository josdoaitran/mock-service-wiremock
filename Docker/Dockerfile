FROM openjdk:8-jre-alpine

EXPOSE 8999

# vars
ENV WIREMOCK_VERSION 2.23.2

# new directories
RUN mkdir /var/wiremock
RUN mkdir /var/wiremock/mappings

COPY stubs /var/wiremock/mappings

# default directory
WORKDIR /var/wiremock

# download wiremock stand alone build
RUN wget -O /var/wiremock/wiremock-standalone.jar https://repo1.maven.org/maven2/com/github/tomakehurst/wiremock-jre8-standalone/$WIREMOCK_VERSION/wiremock-jre8-standalone-$WIREMOCK_VERSION.jar

# start wiremock
ENTRYPOINT ["java","-jar","/var/wiremock/wiremock-standalone.jar","--port","8999","--verbose"]

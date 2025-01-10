# Dokerfile
FROM ubuntu:latest
RUN apt update -y
RUN apt install nginx -y
COPY index.html /opt
ADD https://dlcdn.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.tar.gz /opt
WORKDIR /opt
ENTRYPOINT ["/usr/sbin/nginx"]
CMD [ "-g" , "daemon off;"]
ENV name=ankita
ENV office=cloudblitz
LABEL author=shrivastav
LABEL version=5.80.0
EXPOSE 80

FROM ubuntu:latest
RUN apt update -y && \
    apt upgrade -y && \
    apt install openjdk-8-jdk maven -y && \ 
    rm -rf /var/lib/apt/lists/*
WORKDIR /app
COPY . /app
RUN mvn clean package -Dmaven.test.skip=true
RUN useradd -m shyam
EXPOSE 8080
USER shyam
CMD ["java", "-jar", "target/spring-backend-v1.jar"]

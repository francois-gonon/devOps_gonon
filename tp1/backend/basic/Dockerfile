# backend/basic/Dockerfile
FROM eclipse-temurin:21-jdk-alpine
WORKDIR /app

# Copy source and compile inside the image
COPY Main.java .
RUN javac Main.java

ENTRYPOINT ["java", "Main"]

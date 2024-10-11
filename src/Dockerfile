# Stage 1: Build java program
FROM openjdk:11-jdk-slim

WORKDIR /app

COPY Main.java .

# Compile the program
RUN javac Main.java

# Stage 2: Run app
FROM openjdk:11-jre-slim

WORKDIR /app

COPY --from=0 /app/Main.class .

# Run program
CMD ["java", "Main"]
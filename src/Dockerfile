FROM openjdk:17-jdk-slim AS build

WORKDIR /usr/src/app

# Copy the source file
COPY Main.java .

# Compile the Java program
RUN javac Main.java

# Stage 2: Runtime Stage (using JRE for running the app)
FROM openjdk:17-jre-slim

# Set the working directory in the second stage
WORKDIR /usr/src/app

# Copy the compiled class from the builder stage
COPY --from=builder /usr/src/app/Main.class .

# Command to run the Java program
CMD ["java", "Main"]
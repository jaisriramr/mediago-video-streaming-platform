# ---------- Stage 1: Build ----------
FROM maven:3.9.4-eclipse-temurin-17 AS build

# Set working directory
WORKDIR /app

# Copy pom.xml and download dependencies separately (better caching)
COPY pom.xml .
RUN mvn dependency:go-offline -B

# Copy the entire project
COPY . .

# Package the application (without running tests)
RUN mvn clean package -DskipTests

# ---------- Stage 2: Runtime ----------
FROM eclipse-temurin:17-jre-jammy AS runtime

# Set non-root user for security (optional)
RUN adduser --system --group appuser
USER appuser

# Set work directory
WORKDIR /app

# Copy only the JAR file from build stage
COPY --from=build /app/target/*.jar app.jar

# Expose service port (adjust per service)
EXPOSE 8003

# Run the app
ENTRYPOINT ["java", "-jar", "app.jar"]

# Récupération de l'image
FROM maven:3.9-eclipse-temurin-21 AS build
WORKDIR /app

# copie et préchargement des dépendances Maven
COPY pom.xml .
RUN mvn -B dependency:go-offline

# Copie + compilation 
COPY src ./src
RUN mvn -B clean package -DskipTests

FROM eclipse-temurin:21-jre-alpine
WORKDIR /app

# Copie du jar compilé et commande de run
COPY --from=build /app/target/*.jar app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]
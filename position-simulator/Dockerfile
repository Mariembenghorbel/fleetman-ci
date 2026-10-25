FROM maven:3.8-openjdk-8 AS build
WORKDIR /app
COPY . .
RUN mvn -B -q package -DskipTests

FROM openjdk:8-jre-alpine
COPY --from=build /app/target/*.jar /app.jar
CMD ["java","-jar","/app.jar"]

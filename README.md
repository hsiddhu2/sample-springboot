# Spring Boot HelloWorld Application

This Spring Boot application is created to test deployments on AWS EC2 and ECS using GitHub Actions or AWS CodePipeline.

## Features

- Simple Spring Boot application with a home page.
- Thymeleaf template engine for rendering HTML views.
- Configured for deployment on AWS EC2 and ECS.

## Prerequisites

- Java 17
- Maven
- AWS account
- GitHub account

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/hsiddhu2/springboot-helloworld.git
cd springboot-helloworld
```

### Build the Application

```bash
mvn clean install
```

### Run the Application Locally

```bash
mvn spring-boot:run
```

Access the application at `http://localhost:8080`.

## Deployment

### Deploy to AWS EC2

1. Create an EC2 instance with the required configuration.
2. SSH into the EC2 instance and install Java and Maven.
3. Clone the repository on the EC2 instance.
4. Build and run the application on the EC2 instance.

### Deploy to AWS ECS

1. Create an ECS cluster.
2. Create a Dockerfile for the application.
3. Build and push the Docker image to Amazon ECR.
4. Create an ECS task definition and service.
5. Deploy the application using the ECS service.

## CI/CD with GitHub Actions

1. Create a `.github/workflows` directory in the repository.
2. Add a GitHub Actions workflow file to build and deploy the application.

Example workflow file:

```yaml
name: CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up JDK 17
        uses: actions/setup-java@v2
        with:
          java-version: '17'

      - name: Build with Maven
        run: mvn clean install

      - name: Deploy to AWS EC2
        run: |
          # Add deployment steps here
```

## CI/CD with AWS CodePipeline

1. Create a CodePipeline in the AWS Management Console.
2. Add source, build, and deploy stages to the pipeline.
3. Configure the pipeline to use the repository and build the application.
4. Deploy the application to EC2 or ECS.

## License

This project is licensed under the MIT License.

## Authors

- [hsiddhu2](https://github.com/hsiddhu2)

## Acknowledgments

- Spring Boot documentation
- AWS documentation
- GitHub Actions documentation

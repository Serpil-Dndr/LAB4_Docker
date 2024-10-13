## For the reference for created basic docker-compose.yml  


version: '3.8' # it could be 3 or 3.8

services:
  app:
    image: myapp:latest  # or build from a local Dockerfile using build:
    build:
      context: .
      dockerfile: ./DockerFile
    ports:
      - "8080:80"  # Host port:container port
    volumes:
      - ./app:/app
    environment:
      # You can specify an .env file here
      # Example for the order service
      # Set environment variables for RabbitMQ and other configurations
      - RABBITMQ_CONNECTION_STRING=amqp://guest:guest@localhost:5672/
      - PORT=3000

FROM golang:latest


# Creating Application folder in container
RUN mkdir -p /app

# Setting Home Directory for Application
WORKDIR /app

# Installing Glide Package Manager
RUN apt-get update \
    && apt-get install golang-glide* -y

# Copying Glide.yml
ADD glide.yml /app

# Installing Golang Modules
RUN glide install

# Exporting Ports for Application
EXPOSE 8080 8081

# Creating Volume for Persistent Data
VOLUME ["/app-data"]

# Adding Source Code to Container
ADD . .

# Exporting Environment Varaiables
ENV APPLICATION_ENVIRONMENT DEVELOPMENT

# Running Application
CMD ["go", "application.go"]

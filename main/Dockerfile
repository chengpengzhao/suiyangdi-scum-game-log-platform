# Use the official Node.js image
FROM node:16-slim
# Set the working directory in the container.
WORKDIR /app
COPY package*.json ./ 

# install powershell
###################################
# Prerequisites
# Update the list of packages
RUN  apt-get update
# Install pre-requisite packages.
RUN  apt-get install -y wget
# Download the Microsoft repository GPG keys
RUN wget -q https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
RUN  dpkg -i packages-microsoft-prod.deb
# Delete the Microsoft repository GPG keys file
RUN rm packages-microsoft-prod.deb
# Update the list of packages after we added packages.microsoft.com
RUN  apt-get update
###################################
# Install PowerShell
RUN apt-get install -y powershell

# Install redis-cli
RUN apt-get install -y redis-tools

RUN npm install
COPY . .
EXPOSE 10000 

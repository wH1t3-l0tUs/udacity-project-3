# Use NodeJS base image from DockerHub
FROM node:12

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies in the container
RUN npm ci 

# Copy the rest of your app's source code to the working directory
COPY . .

# Expose port 8080
EXPOSE 8080

# Command to run the app
CMD [ "npm", "run", "prod" ]
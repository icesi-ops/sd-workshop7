# Use an official Node.js image as a parent image
FROM node:8.17.0

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package*.json ./
RUN npm install

# Bundle app source
COPY . .

# Expose the port the app runs on
EXPOSE 8080

# Define environment variable
ENV PORT 8080
ENV AUTH_API_ADDRESS http://auth-api:8000
ENV TODOS_API_ADDRESS http://todos-api:8082

# Command to run the application
CMD ["npm", "start"]

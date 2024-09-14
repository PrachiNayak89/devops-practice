# Building on the nodeJS image
FROM node:22-alpine3.19

# Copy the source code to container directory
COPY package.json /app/
COPY src /app/

# Setting up the working directory
WORKDIR /app

# Installing the dependency
RUN npm install

# Running the application and last command
CMD ["node", "server.js"]

# docker build node-app:1.0 . 
# docker run -d -p 3000:3000 node-app:1.0 

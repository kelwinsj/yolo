# Using the official Node.js Alpine image
FROM node:13.12.0-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json files
COPY package*.json .

# Install all the dependencies specified in the package.json file
RUN npm install

# Copy all the files to the working directory in the container
COPY . .

# Expose port 5000 to allow incoming connections to the container
EXPOSE 5000

# Run the app when the container starts
CMD ["npm", "start"]
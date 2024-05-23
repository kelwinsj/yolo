# Using the official Node.js Alpine image
FROM node:13.12.0-alpine AS builder

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json files
COPY package*.json .

# Install all the dependencies specified in the package.json file
RUN npm install --production

# Copy all the files to the working directory in the container
COPY . .

# Building the application 
RUN npm run build

# Start a new stage
FROM node:13.12.0-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy only the necessary files from the builder stage
COPY --from=builder /app ./

# Expose port 3000 to allow incoming connections to the container
EXPOSE 3000

# Run the app when the container starts
CMD ["npm", "start"]
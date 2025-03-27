# Use Node.js as the base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first to leverage Docker caching
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the frontend app
COPY . .

# Build the frontend (assuming React or similar framework)
RUN npm run build

# Expose the port the app runs on
EXPOSE 3000

# Start the frontend application
CMD ["npm", "start"]


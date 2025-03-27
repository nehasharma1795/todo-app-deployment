# Use Node.js as the base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Install extra dependencies needed for npm build (Alpine fix)
RUN apk add --no-cache python3 g++ make

# Copy package.json and package-lock.json first to leverage Docker caching
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the frontend app
COPY . .

# Build the frontend
RUN npm run build

# Expose the port the frontend runs on
EXPOSE 3000

# Start the frontend application
CMD ["npm", "start"]


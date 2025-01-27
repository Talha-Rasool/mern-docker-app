


# Use the official Node.js image as the base
FROM node:18

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the backend source code
COPY . .

# Expose port 5050 (the backend port)
EXPOSE 5050

# Set environment variable for MongoDB connection (placeholder)
ENV MONGO_URI=mongodb://mongo:27017/mydatabase

# Start the backend server
CMD ["npm", "start"]


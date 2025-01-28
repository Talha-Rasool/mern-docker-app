# Description: Dockerfile for the client side of the MERN stack application


# Stage 1: Build the React app
FROM node:16 AS build

# Set the working directory 
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Set the environment variable for the API URL
ENV REACT_APP_API_URL=http://backend:5050


# Build the React app for production
RUN npm run build

# Stage 2: Serve the built app
FROM nginx:alpine

# Copy the build files from the build stage
COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 for the web server
EXPOSE 80



# Start nginx server
CMD ["nginx", "-g", "daemon off;"]


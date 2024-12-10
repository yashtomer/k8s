# Stage 1: Build Stage
FROM node:20-alpine AS build

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the entire application source code to the container
COPY . .

# Build the Angular app for production
RUN npm run build:prod

# Stage 2: Serve Stage
FROM nginx:stable-alpine

# Copy the built Angular files from the previous stage
COPY --from=build /app/dist/frontend/browser /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
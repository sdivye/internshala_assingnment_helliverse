# Stage 1: Build the AngularJS app
FROM node:18 AS builder

# Set the working directory for the builder stage
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the AngularJS app
RUN npm run build --prod

# Stage 2: Serve the built app using a lightweight web server
FROM nginx

# Set the working directory for the final stage
WORKDIR /usr/share/nginx/html

# Copy the built app from the builder stage to the NGINX web server directory
COPY --from=builder app/dist/my-first-project /usr/share/nginx/html/dashboard

# Expose the default NGINX port
EXPOSE 80

# Start NGINX
CMD ["nginx", "-g", "daemon off;"]

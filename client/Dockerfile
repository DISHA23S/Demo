# Use the official Node.js image.
FROM node:18

# Set the working directory.
WORKDIR /usr/src/app

# Copy package.json and package-lock.json.
COPY client/package*.json ./

# Install dependencies.
RUN npm install

# Copy the rest of the application.
COPY client/ .

# Build the React application.
RUN npm run build

# Use a smaller image for serving the app.
FROM nginx:alpine

# Copy the build artifacts from the previous stage.
COPY --from=0 /usr/src/app/build /usr/share/nginx/html

# Expose the port nginx is running on.
EXPOSE 80

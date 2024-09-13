# Use the official Node.js image.
FROM node:18

# Set the working directory.
WORKDIR /usr/src/app

# Copy package.json and package-lock.json.
COPY server/package*.json ./

# Install dependencies.
RUN npm install

# Copy the rest of the application.
COPY server/ .

# Expose the port the app runs on.
EXPOSE 5000

# Command to run the app.
CMD ["npm", "start"]

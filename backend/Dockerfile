# Use Node.js as the base image
FROM node:16

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first to leverage Docker cache
COPY package*.json ./

# Install backend dependencies
RUN npm install --production

# Copy the rest of the backend code
COPY . .

# Expose backend server port
EXPOSE 5000

# Run the backend server
CMD ["node", "server.js"]

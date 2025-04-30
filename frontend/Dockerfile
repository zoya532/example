# Use Node.js as the base image
FROM node:16

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Set environment to production
ENV NODE_ENV=production

# Install frontend dependencies
RUN npm install --production

# Copy the rest of the frontend code
COPY . .

# Build the production-ready React app
RUN npm run build

# Install a lightweight HTTP server globally
RUN npm install -g serve

# Expose the frontend app port
EXPOSE 3000

# Serve the build folder in production mode
CMD ["serve", "-s", "build", "-l", "3000"]

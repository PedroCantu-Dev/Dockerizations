# Use the Node.js 22-alpine image as the base image
FROM node:22-alpine

# Set the working directory inside the container
WORKDIR /app

# Install Vite globally
RUN npm install -g vite

# Verify the installation (optional, can be removed in production)
# RUN vite --version

# Expose the default Vite port
EXPOSE 5173

# Default command (can be adjusted based on your project setup)
CMD ["sh"]

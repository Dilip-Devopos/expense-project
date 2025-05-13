FROM node:18-alpine

# Create app directory
WORKDIR /app

# Install serve globally
RUN npm install -g serve

# Copy the build folder (assumes Jenkins copied it)
COPY build /app/build

# Expose port 3000
EXPOSE 3000

# Serve the build folder
CMD ["serve", "-s", "build", "-l", "3000"]

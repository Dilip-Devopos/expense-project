# Step 1: Use NGINX to serve the build (no build step here)
FROM nginx:stable-alpine

# Step 2: Remove the default nginx index page
RUN rm -rf /usr/share/nginx/html/*

# Step 3: Copy the pre-built frontend build directory into the container
# Ensure that the build folder is in the same directory as your Dockerfile
COPY build /usr/share/nginx/html

# Step 4: Expose the default port for NGINX
EXPOSE 80

# Step 5: Start the NGINX server
CMD ["nginx", "-g", "daemon off;"]

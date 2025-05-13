# Step 1: Use NGINX to serve the build
FROM nginx:stable-alpine

# Step 2: Remove the default nginx index page
RUN rm -rf /usr/share/nginx/html/*

# Step 3: Copy the full contents of the React build directory
COPY build/ /usr/share/nginx/html/

# Step 4: Expose the default port for NGINX
EXPOSE 80

# Step 5: Start the NGINX server
CMD ["nginx", "-g", "daemon off;"]

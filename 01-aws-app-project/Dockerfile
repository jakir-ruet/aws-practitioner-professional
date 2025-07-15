# Use lightweight NGINX Alpine image
FROM nginx:alpine

# Remove default NGINX static files
RUN rm -rf /usr/share/nginx/html/*

# Copy your static website files to NGINX folder
COPY index.html /usr/share/nginx/html/

# Expose port 80
EXPOSE 80

# Start NGINX server
CMD ["nginx", "-g", "daemon off;"]

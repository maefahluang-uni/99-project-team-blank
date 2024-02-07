# Use a base image
FROM nginx:alpine

# Copy HTML and CSS files to nginx default directory
COPY index.html /usr/share/nginx/html/
COPY css/styles.css /usr/share/nginx/html/

# Expose port 80
EXPOSE 80
# Use lightweight nginx image
FROM nginx:alpine

# Remove default nginx config
RUN rm /etc/nginx/conf.d/default.conf

# Create custom nginx config that listens on Render's PORT
RUN echo 'server { \
    listen 10000; \
    location / { \
        root /usr/share/nginx/html; \
        index index.html; \
    } \
}' > /etc/nginx/conf.d/default.conf

# Copy your HTML file into nginx
COPY index.html /usr/share/nginx/html/index.html

# Expose required port
EXPOSE 10000

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
# Simple static site served via nginx
FROM nginx:1.29-alpine

# Pull in the latest patched OS packages (fixes CVEs in c-ares, curl,
# openssl, libxml2, libexpat, nghttp2 etc. that ship in the base image)
RUN apk update && apk upgrade --no-cache

# Remove default nginx static assets
RUN rm -rf /usr/share/nginx/html/*

# Copy app files into nginx's web root
COPY index.html /usr/share/nginx/html/
COPY style.css /usr/share/nginx/html/
COPY script.js /usr/share/nginx/html/

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

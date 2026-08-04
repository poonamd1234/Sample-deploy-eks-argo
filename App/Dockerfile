# Simple static site served via nginx (non-root variant, listens on 8080)
FROM nginxinc/nginx-unprivileged:1.29-alpine

USER root

# Pull in the latest patched OS packages (fixes CVEs in c-ares, curl,
# openssl, libxml2, libexpat, nghttp2 etc. that ship in the base image)
RUN apk update && apk upgrade --no-cache

# Remove default nginx static assets (root-owned, so must run before USER nginx)
RUN rm -rf /usr/share/nginx/html/*

# Copy app files into nginx's web root
COPY index.html /usr/share/nginx/html/
COPY style.css /usr/share/nginx/html/
COPY script.js /usr/share/nginx/html/

# Drop privileges for the actual runtime user
USER nginx

EXPOSE 8080

HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD wget -qO- http://127.0.0.1:8080/ || exit 1

CMD ["nginx", "-g", "daemon off;"]

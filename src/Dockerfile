FROM nginx:latest

RUN rm -rf /usr/share/nginx/html/* && apt-get update && apt-get install -y curl

EXPOSE 80

HEALTHCHECK \
    --interval=30s \
    --timeout=30s \
    --start-period=5s \
    --retries=3 \
    CMD ["curl", "-s","http://localhost/"] || exit 1

COPY . /usr/share/nginx/html/

CMD [ "nginx","-g","daemon off;"]
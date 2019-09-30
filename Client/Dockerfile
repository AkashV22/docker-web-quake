FROM alpine AS web-quake
RUN mkdir /repo && \
    apk --no-cache add git && \
    git clone https://github.com/Triang3l/WebQuake.git /repo

FROM nginx:mainline-alpine
COPY --from=web-quake /repo/Client /usr/share/nginx/html
RUN rm -f /usr/share/nginx/html/index.html

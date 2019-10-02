FROM alpine AS web-quake
RUN mkdir /repo && \
    apk --no-cache add git && \
    git clone https://github.com/Triang3l/WebQuake.git /repo

FROM node:alpine
WORKDIR /usr/src/app
COPY --from=web-quake /repo/Server .
RUN npm install websocket
ENTRYPOINT [ "node", "WebQDS.js", "-port", "80" ]

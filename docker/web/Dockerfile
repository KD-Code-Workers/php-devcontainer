#FROM nginx:alpine
FROM nginx:stable-alpine-slim
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID
RUN addgroup -g $USER_GID -S $USERNAME && adduser -u $USER_UID -s /bin/sh -S -G $USERNAME $USERNAME
#USER $USERNAME
RUN apk add --no-cache \
    github-cli~=2 && \
    rm -fr /var/cache/apk
COPY default.conf /etc/nginx/conf.d/default.conf
WORKDIR /home/$USERNAME


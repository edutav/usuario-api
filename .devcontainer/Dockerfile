FROM node:lts-alpine

RUN npm i -g @nestjs/cli

RUN apk update && \
    apk upgrade && \
    apk add git

ARG USER_UID=1000
ARG USER_GID=$USER_UID
ARG USERNAME=node

RUN if [ "$USER_GID" != "1000" ] || [ "$USER_UID" != "1000" ]; then \
        groupmod --gid $USER_GID $USERNAME \
        && usermod --uid $USER_UID --gid $USER_GID $USERNAME \
        && chown -R $USER_UID:$USER_GID /home/$USERNAME; \
    fi

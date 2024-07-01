FROM node:20-alpine3.19

ARG USERNAME=vscode

RUN apk add -q --update --progress --no-cache \
    git sudo openssh-client bash \
    py3-pip gcc musl-dev python3-dev libffi-dev openssl-dev cargo make \
 && pip install --break-system-packages azure-cli

RUN addgroup $USERNAME \
 && adduser -G $USERNAME $USERNAME -D \
 && echo "$USERNAME ALL=\(root\) NOPASSWD:ALL" > /etc/sudoers.d/$USERNAME \
 && chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME
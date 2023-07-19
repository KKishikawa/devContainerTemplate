FROM mcr.microsoft.com/vscode/devcontainers/base:bookworm
ARG NODE_VER=lts
RUN apt -y update && apt -y upgrade && apt -y install curl
RUN mkdir /workspaces && chown vscode:vscode /workspaces

USER vscode
ENV NVM_DIR=/home/vscode/.nvm
ENV PATH $PATH:${NVM_DIR}
RUN bash -c "curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash"
RUN bash -c "source ${NVM_DIR}/nvm.sh && nvm install ${NODE_VER} && nvm use ${NODE_VER} "

ENTRYPOINT tail -f /dev/null

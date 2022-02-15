FROM nvcr.io/nvidia/tensorflow:22.01-tf2-py3

COPY .devcontainer/library-scripts/git-branch.sh /etc/bash.bashrc
# RUN ./etc/bash.bashrc

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

#  Color change of bash prompt

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME



USER $USERNAME

ENV SHELL /bin/bash

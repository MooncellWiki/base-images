FROM rust:1.77-bookworm

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    # Remove imagemagick due to https://security-tracker.debian.org/tracker/CVE-2019-10131
    && apt-get purge -y imagemagick imagemagick-6-common

ARG USER_UID=1000
ARG USER_GID=${USER_UID}
ARG USERNAME=vscode
# Add a non-root user and allow them to become root or postgres
RUN groupadd -g $USER_GID $USERNAME \
    && useradd -s /bin/bash -u $USER_ID -g $USER_GID -m $USERNAME || echo "User already exists." \
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root, postgres\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

RUN cargo install sea-orm-cli
RUN chown -R $USERNAME:$USERNAME /usr/local/cargo/registry
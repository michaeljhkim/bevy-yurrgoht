FROM quay.io/pypa/manylinux_2_34_x86_64

WORKDIR /workspaces


# Install necessary build tools and libraries
RUN dnf install -y \
    mesa-vulkan-drivers vulkan-tools vulkan-loader-devel vulkan-validation-layers glslang glslc spirv-tools \
    git wget doxygen p7zip p7zip-plugins \
    gcc-c++ libX11-devel alsa-lib-devel systemd-devel \
    wayland-devel libxkbcommon-devel \
    alsa-lib-devel.x86_64
RUN dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo && \
    dnf install -y docker

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y


# Default command: Start bash to interact with the container
CMD ["/bin/bash"]
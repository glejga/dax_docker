

FROM ubuntu-debootstrap:trusty

# Install the MCR dependencies and some things we'll need and download the MCR
# from Mathworks -silently install it
RUN apt-get -qq update && apt-get -qq install -y \
    unzip \
    xorg \
    wget \
    curl && \
    mkdir /mcr-install && \
    mkdir /opt/mcr && \
    cd /mcr-install && \
    wget http://www.mathworks.com/supportfiles/downloads/R2016a/deployment_files/R2016a/installers/glnxa64/MCR_R2016a_glnxa64_installer.zip && \
    cd /mcr-install && \
    unzip -q MCR_R2016a_glnxa64_installer.zip && \
    ./install -destinationFolder /opt/mcr -agreeToLicense yes -mode silent && \
    cd / && \
    rm -rf mcr-install

# Configure environment variables for MCR
ENV LD_LIBRARY_PATH /opt/mcr/v90/runtime/glnxa64:/opt/mcr/v90/bin/glnxa64:/opt/mcr/v90/sys/os/glnxa64
ENV XAPPLRESDIR /opt/mcr/v90/X11/app-defaults
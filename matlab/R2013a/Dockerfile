#See https://github.com/vistalab/docker/tree/master/matlab/runtime/2013a

FROM ubuntu-debootstrap:trusty
RUN apt-get -qq update && apt-get -qq install -y unzip xorg wget curl && \
    mkdir /opt/mcr && \
    mkdir /mcr-install && \
    cd /mcr-install && \
    wget -nv http://www.mathworks.com/supportfiles/MCR_Runtime/R2013a/MCR_R2013a_glnxa64_installer.zip && \
    unzip MCR_R2013a_glnxa64_installer.zip && \
    ./install -destinationFolder /opt/mcr -agreeToLicense yes -mode silent && \
    cd / && \
    rm -rf /mcr-install

# Configure environment variables for MCR
ENV LD_LIBRARY_PATH /opt/mcr/v81/runtime/glnxa64:/opt/mcr/v81/bin/glnxa64:/opt/mcr/v81/sys/os/glnxa64:/opt/mcr/v81/sys/java/jre/glnxa64/jre/lib/amd64/native_threads:/opt/mcr/v81/sys/java/jre/glnxa64/jre/lib/amd64/server:/opt/mcr/v81/sys/java/jre/glnxa64/jre/lib/amd64
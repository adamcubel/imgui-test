# Source from SPL Build Image
FROM ibcs-jfrog.gtri.gatech.edu/shorad-docker-dev/spl-rhel8-rti:latest

# Artifactory username and password passed in from .devcontainer.json
# Retrieved from local dev machine ENV vars at container build time
ARG ART_USERNAME
ARG ART_PASSWORD

# Install developer tools for dev container
RUN dnf install -y \
                git \
                make \
                cmake3 \
                boost-devel \
                log4cxx-devel \
                pugixml-devel \
                openssl-devel \
                findutils \
                nmap

# Copy over Artifactory repo files if they exist
COPY art_repos/*artifactory.repo /etc/yum.repos.d/
RUN echo ${ART_USERNAME} > /etc/yum/vars/ART_USERNAME
RUN echo ${ART_PASSWORD} > /etc/yum/vars/ART_PASSWORD

# Disable FIPS so that RTI DDS can install 
RUN /usr/bin/fips-mode-setup --disable

# Install dependent SPL libs
# RUN dnf install -y --skip-broken \
#                 spl-libs-devel \
#                 spl-link16-devel \
#                 spl-log-console-devel \
#                 spl-transport-devel \
#                 spl-exchange-sendreceive-devel \
#                 spl-converter-c2link16-devel \
#                 spl-c2-devel

RUN echo "export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib/" >> ~/.bash_profile
FROM ubuntu:18.04
# Set i386
RUN dpkg --add-architecture i386
RUN apt update

#install inferno i386 deps
RUN apt-get --reinstall install -y  libx11-6:i386 libx11-dev:i386 libxext-dev:i386

# install tools
RUN apt-get install -y vim git gcc g++-multilib

#Structure file system and pull inferno 
ARG infernoInstDir=/proj
RUN mkdir $infernoInstDir
RUN cd $infernoInstDir && git clone https://bitbucket.org/inferno-os/inferno-os.git

#Setup inferno build vars
ARG infernoRoot=$infernoInstDir/inferno-os
ENV INFERNO_ROOT=$infernoRoot
ENV SYSHOST="Linux"
ENV objtype="386"
ENV PATH="$INFERNO_ROOT/$SYSHOST/$objtype/bin:$PATH"
COPY mkconfig $infernoRoot/

# Build inferno
RUN cd $infernoRoot && ./makemk.sh && mk -s nuke mkdirs install

CMD ["bash"]

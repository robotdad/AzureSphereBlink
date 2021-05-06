FROM mcr.microsoft.com/azurespheresdk:latest AS dev
RUN apt remove cmake -y
RUN wget https://github.com/Kitware/CMake/releases/download/v3.20.2/cmake-3.20.2-linux-x86_64.sh 
RUN sh cmake-3.20.2-linux-x86_64.sh --prefix=/usr/local/ --exclude-subdir 
RUN rm cmake-3.20.2-linux-x86_64.sh

FROM dev AS debug-build
COPY ./ /src/
WORKDIR /src
RUN cmake --preset="Debug-Build-Linux"
ENTRYPOINT [ "ninja", "-C", "build/Release-Build-Linux"]

FROM dev AS release-build
COPY ./ /src/
WORKDIR /src
RUN cmake --preset="Release-Build-Linux"
ENTRYPOINT [ "ninja", "-C", "build/Release-Build-Linux" ]
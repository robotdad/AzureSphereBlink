FROM mcr.microsoft.com/azurespheresdk:latest AS dev

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
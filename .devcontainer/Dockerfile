FROM mcr.microsoft.com/azurespheresdk:latest AS dev

FROM dev AS debug-build
COPY ./ /src/
WORKDIR /src
RUN cmake --preset="Debug-Linux"
ENTRYPOINT [ "cmake", "--buld", "--preset=Debug-Build-Linux"]

FROM dev AS release-build
COPY ./ /src/
WORKDIR /src
RUN cmake --preset="Release-Linux"
ENTRYPOINT [ "cmake", "--build", "--preset=Release-Build-Linux" ]
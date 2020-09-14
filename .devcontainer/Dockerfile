FROM mcr.microsoft.com/azurespheresdk:latest AS dev

FROM dev AS build
COPY ./ /src/
WORKDIR /out
RUN cmake -G "Ninja" -DCMAKE_TOOLCHAIN_FILE="/opt/azurespheresdk/CMakeFiles/AzureSphereToolchain.cmake" \
    -DAZURE_SPHERE_TARGET_API_SET="latest-lts" -DCMAKE_BUILD_TYPE="Release" "/src"
ENTRYPOINT [ "ninja" ]
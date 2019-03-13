# Clone Repository
FROM alpine AS code
MAINTAINER knight

RUN apk update
RUN apk add git
WORKDIR /repository
RUN git clone https://github.com/knight720/TestDotNet.git

# Build Application
FROM microsoft/dotnet:2.2-sdk AS build
WORKDIR /app

## copy csproj and restore as distinct layers
COPY --from=code /repository/TestDotNet/032_Sample_with_Container/*.sln .
COPY --from=code /repository/TestDotNet/032_Sample_with_Container/WebApplication1/*.csproj ./WebApplication1/
RUN dotnet restore

# copy everything else and build app
COPY --from=code /repository/TestDotNet/032_Sample_with_Container/WebApplication1/. ./WebApplication1/
WORKDIR /app/WebApplication1
RUN dotnet publish -c Release -o out

# Deploy Application
FROM microsoft/dotnet:2.2-aspnetcore-runtime AS runtime
WORKDIR /app
COPY --from=build /app/WebApplication1/out ./
ENTRYPOINT ["dotnet", "WebApplication1.dll"]

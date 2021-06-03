FROM public.ecr.aws/lambda/dotnet:5.0 AS base

FROM mcr.microsoft.com/dotnet/sdk:5.0-buster-slim as build
WORKDIR /src
COPY ["ServerlessContainer.csproj", "ServerlessContainer/"]
RUN dotnet restore "ServerlessContainer/ServerlessContainer.csproj"

WORKDIR "/src/ServerlessContainer"
COPY . .
RUN dotnet build "ServerlessContainer.csproj" --configuration Release --output /app/build

FROM build AS publish
RUN dotnet publish "ServerlessContainer.csproj" \
            --configuration Release \ 
            --runtime linux-x64 \
            --self-contained false \ 
            --output /app/publish \
            -p:PublishReadyToRun=true  

FROM base AS final
WORKDIR /var/task
COPY --from=publish /app/publish .
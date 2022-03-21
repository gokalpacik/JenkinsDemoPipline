#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

RUN curl -fsSLO  https://get.docker/builds/Linux/x86_64/docker-17.04.0-ce.tgz  \
  && tar xzvf docker-17.04.0-ce.tgz \
  && mv docker/docker /usr/local/bin \
  && rm -r docker docker-17.04.0-ce.tgz

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["JenkinsDemoPipline/JenkinsDemoPipline.csproj", "JenkinsDemoPipline/"]
RUN dotnet restore "JenkinsDemoPipline/JenkinsDemoPipline.csproj"
COPY . .
WORKDIR "/src/JenkinsDemoPipline"
RUN dotnet build "JenkinsDemoPipline.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "JenkinsDemoPipline.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "JenkinsDemoPipline.dll"]

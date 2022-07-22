#Gets the dot net SDK to use
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
#Setting the working directory inside the docker image
WORKDIR /app

EXPOSE 5000
#Copies ONLY csproj files into the image
COPY **/*.csproj ./
#Restores those files
RUN dotnet restore
#Copies everything into the image
COPY . ./
#Builds and publishes the code in release mode - outputs into 'bin'
RUN dotnet publish -c Release -o /app/publish

ENTRYPOINT ["dotnet", "publish/WeatherApi.dll"]
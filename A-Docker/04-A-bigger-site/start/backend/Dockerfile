FROM mcr.microsoft.com/dotnet/sdk:9.0-alpine AS build

WORKDIR /src

COPY backend.csproj .

# set the current directory to `/src`
# copy the manifest file: backend.csproj into this directory
# from a shell, run `dotnet restore`
# copy the source files into place
# from a shell, run `dotnet build -c Release`
# from a shell, run `dotnet publish -c Release -o /app`

COPY . .

RUN dotnet build -c Release
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/aspnet:9.0-alpine

ENV ASPNETCORE_URLS=http://+:5000
EXPOSE 5000

WORKDIR /app

COPY --from=build /app .

CMD ["dotnet", "backend.dll"]
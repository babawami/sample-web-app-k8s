FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build

WORKDIR /app

# Copy csproj and restore as distinct layers
COPY . ./
RUN dotnet restore Basic3TierAPI/Basic3TierAPI.csproj
# Copy everything else and build
RUN dotnet publish Basic3TierAPI/Basic3TierAPI.csproj -c Release -o /out

# Debugging step to list the contents of the /app/out directory in the build stage
RUN ls -la /out

# Build runtime image
# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:7.0
WORKDIR /app
COPY --from=build /out ./
ENTRYPOINT ["dotnet", "Basic3TierAPI.dll"]

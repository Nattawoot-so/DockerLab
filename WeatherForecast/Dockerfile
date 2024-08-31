# Use the official .NET Core SDK as a parent image
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /APIWithDocker

# Copy the project fileand restore any dependencies (use .csproj for the project name)
COPY *.csproj ./
RUN dotnet restore

# Copy the rest of the application code
COPY . .

# Publish the application
RUN dotnet publish -c Release -o /app

# Build the runtime image
# FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS runtime
# WORKDIR /APIWithDocker
# COPY --from=build /APIWithDocker/out .

# Expose the port your application will run on
# EXPOSE 8080

# Start the application
# ENTRYPOINT ["dotnet", "APIWithDocker.dll"]

# final stage/image
FROM mcr.microsoft.com/dotnet/aspnet:7.0 AS runtime
EXPOSE 80
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["./APIWithDocker"]
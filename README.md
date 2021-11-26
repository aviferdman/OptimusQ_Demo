# ASP.NET Core Demo App

## Description

 - This application can be used to demonstrates how to build container images for ASP.NET Core web apps for Linux and Windows containers, for x64, ARM32 and ARM64 architectures.

## Build

- To restore the application dependencies use:

```
dotnet restore
```

- To build the application and publish the output on the "/app" directory use the following command:

```
dotnet publish -c release -o /app --no-restore
```

## Usage

- To run the application just run the dll by using:

```
dotnet aspnetapp.dll
```

- Then you should be able to access the application on port 80:
```
http://localhost


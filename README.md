
# Deploy a .NET app on Clever Cloud

This is a .NET example app to test deployments on Clever Cloud.

## Deploy this app

1. Clone this repository
2. Create a new app on Clever Cloud (from the console or using [the CLI](https://www.clever-cloud.com/doc/getting-started/cli/))
3. Choose a .NET runtime and follow the setting process
4. Check that you have the following environment variables injected: 

```
ASPNETCORE_URLS="http://0.0.0.0:8080"
CC_CACHE_DEPENDENCIES="true"
CC_DOTNET_VERSION="6.0"
```

5. Copy the git push command provided by the console and paste it at the root of this repository. Time to deploy

💡 If you are encountering Git errors on push, try `git push clever main:master`

## Want to make your own .NET app from scratch?

Use the following commands:

```bash
dotnet new webapp -n MyWebApp
cd MyWebApp
dotnet publish -c Release MyWebApp.csproj
```

See your app on localhost with `dotnet bin/Release/net6.0/publish/MyWebApp.dll`


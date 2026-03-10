
# Deploy a .NET app on Clever Cloud

This is a .NET example app to test deployments on Clever Cloud. Find more information about .NET deployment in [Clever Cloud Documentation](https://www.clever-cloud.com/doc/deploy/application/dotnet/dotnet/#configure-your-dotnet-application).

## Deploying on Clever Cloud

You have two options to deploy your application on Clever Cloud: using the Web Console or using the Clever Tools CLI.

### Option 1: Deploy using the Web Console

1. Log in to the [Clever Cloud console](https://console.clever-cloud.com/)
2. Click on "Create" and select "An application"
3. Choose ".NET" as the runtime environment
4. Configure your application settings (name, region, etc.)
5. Add the following environment variables:

```
ASPNETCORE_URLS="http://0.0.0.0:8080"
CC_CACHE_DEPENDENCIES="true"
CC_DOTNET_VERSION="8.0"
```

6. Deploy using Git:

```bash
git remote add clever git+ssh://git@push-par-clevercloud-customers.services.clever-cloud.com/app_<your-app-id>.git
git push clever main:master
```

### Option 2: Deploy using Clever Tools CLI

#### 1. Install Clever Tools

Install the Clever Tools CLI following the [official documentation](https://www.clever-cloud.com/doc/clever-tools/getting_started/):

```bash
# Using npm
npm install -g clever-tools

# Or using Homebrew (macOS)
brew install clever-tools
```

#### 2. Log in to your Clever Cloud account

```bash
clever login
```

#### 3. Create a new application

```bash
clever create --type dotnet <YOUR_APP_NAME>

clever env set ASPNETCORE_URLS "http://0.0.0.0:8080"
clever env set CC_CACHE_DEPENDENCIES "true"
clever env set CC_DOTNET_VERSION "8.0"
```

#### 4. Deploy your application

```bash
clever deploy
```

#### 5. Open your application

```bash
clever open
```

### Monitoring Your Application

- **Web Console**: The Clever Cloud console provides logs, metrics, and other tools to manage your application.
- **CLI**: Use `clever logs` to view application logs and `clever status` to check the status of your application.

## Want to make your own .NET app from scratch?

Use the following commands:

```bash
dotnet new webapp -n MyWebApp
cd MyWebApp
dotnet publish -c Release MyWebApp.csproj
```

See your app on localhost with `dotnet bin/Release/net8.0/publish/MyWebApp.dll`

Happy deployments ✌️


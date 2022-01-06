# Snippets

## Docker SSL Dev certs for ASP.NET Core
Docker SSL dev certs for ASP.NET Core 

https://docs.microsoft.com/en-us/aspnet/core/security/docker-https?view=aspnetcore-6.0

## Build VS/Rider created Docker files

To build outside VS/Rider go to parent directory of project e.g. src where structure is src/MyProject , run "docker build -f MyProject/Dockerfile ." don't forget "." at the end


## Azure Container Apps

Don't use portal, Preview doesn't give options for environment variable.

To create via CLI:
1. Install extension
  az extension add \
    --source https://workerappscliextension.blob.core.windows.net/azure-cli-extension/containerapp-0.2.0-py2.py3-none-any.whl
  
  az provider register --namespace Microsoft.Web
  
2. After creating resource group and environment can use the following command to create container app:

az containerapp create --image "<IMAGE URL>" --name "<NAME>" --resource-group "<RESOURCE GROUP>" --environment "<ENVIRONMENT>" --environment-variables "ASPNETCORE_HTTP_PORT=80,ASPNETCORE_URLS=http://+" --ingress external --target-port 80

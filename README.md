# JJAzure Azure ServiceFabric Mesh
Playground for Azure ServiceFabric Mesh

## Application on DotNet Core 
Create new SF Mesh application from Visual Studio 2017

Start Docker with Windows Containers.

Solution contains services: Web API app and Console app.

Definition of deployment

- App Resources for application - app, network, gateway
- App Resources in each project - service definition

Note: If you have problem with deployment to Mesh, check your parameters.yaml to contains only whole numbers (without decimals)

### Debug locally
Just hit Run on ServiceFarbic local cluster and you can debug your service.

### Deploy to Azure
Click on Publish on SF project and it will automatically deploy to Azure.

Setup Azure CLI for Mesh https://docs.microsoft.com/en-us/azure/service-fabric-mesh/service-fabric-mesh-howto-setup-cli

To get Ip address of gateway call this OR check deployment Output blade in Azure portal

```azurecli-interactive
rg=MeshApp-rg
az mesh gateway show --resource-group $rg --name ApplicationDotNetCoreGateway
```

Run browser http://<your-ip>:8080/api/values
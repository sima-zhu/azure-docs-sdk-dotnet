---
title: Azure AppService Management client library for .NET
keywords: Azure, dotnet, SDK, API, Azure.ResourceManager.AppService, websites
author: pallavit
ms.author: pallavit
ms.date: 08/29/2022
ms.topic: reference
ms.devlang: dotnet
ms.service: websites
---
# Azure AppService Management client library for .NET - version 1.0.0-beta.4 


This package follows the [new Azure SDK guidelines](https://azure.github.io/azure-sdk/general_introduction.html),which provide core capabilities that are shared amongst all Azure SDKs, including:

- The intuitive Azure Identity library.
- An HTTP pipeline with custom policies.
- Error handling.
- Distributed tracing.

## Getting started 

### Install the package

Install the Azure AppService management library for .NET with [NuGet](https://www.nuget.org/):

```dotnetcli
dotnet add package Azure.ResourceManager.AppService --prerelease
```

### Prerequisites
Set up a way to authenticate to Azure with Azure Identity.

Some options are:
- Through the [Azure CLI Login](/cli/azure/authenticate-azure-cli).
- Via [Visual Studio](/dotnet/api/overview/azure/identity-readme?view=azure-dotnet#authenticating-via-visual-studio).
- Setting [Environment Variables](https://github.com/Azure/azure-sdk-for-net/blob/Azure.ResourceManager.AppService_1.0.0-beta.4/sdk/resourcemanager/Azure.ResourceManager/docs/AuthUsingEnvironmentVariables.md).

More information and different authentication approaches using Azure Identity can be found in [this document](/dotnet/api/overview/azure/identity-readme?view=azure-dotnet).

### Authenticate the Client

To create an authenticated client and start interacting with Azure resources, please see the [quickstart guide here](https://github.com/Azure/azure-sdk-for-net/blob/Azure.ResourceManager.AppService_1.0.0-beta.4/doc/dev/mgmt_quickstart.md)

## Key concepts

Key concepts of the Azure .NET SDK can be found [here](https://github.com/Azure/azure-sdk-for-net/blob/Azure.ResourceManager.AppService_1.0.0-beta.4/sdk/resourcemanager/Azure.ResourceManager/README.md#key-concepts)

## Documentation

Documentation is available to help you learn how to use this package

- [Quickstart](https://github.com/Azure/azure-sdk-for-net/blob/Azure.ResourceManager.AppService_1.0.0-beta.4/doc/dev/mgmt_quickstart.md)
- [API References](/dotnet/api/?view=azure-dotnet)
- [Authentication](https://github.com/Azure/azure-sdk-for-net/blob/Azure.ResourceManager.AppService_1.0.0-beta.4/sdk/identity/Azure.Identity/README.md)

## Examples

Code samples for using the management library for .NET can be found in the following locations
- [.NET Management Library Code Samples](/samples/browse/?branch=master&languages=csharp&term=managing%20using%20Azure%20.NET%20SDK)

## Troubleshooting

-   File an issue via [Github
    Issues](https://github.com/Azure/azure-sdk-for-net/issues)
-   Check [previous
    questions](https://stackoverflow.com/questions/tagged/azure+.net)
    or ask new ones on Stack Overflow using azure and .net tags.


## Next steps

For more information on Azure SDK, please refer to [this website](https://azure.github.io/azure-sdk/)

## Contributing

For details on contributing to this repository, see the [contributing
guide][cg].

This project welcomes contributions and suggestions. Most contributions
require you to agree to a Contributor License Agreement (CLA) declaring
that you have the right to, and actually do, grant us the rights to use
your contribution. For details, visit <https://cla.microsoft.com>.

When you submit a pull request, a CLA-bot will automatically determine
whether you need to provide a CLA and decorate the PR appropriately
(e.g., label, comment). Simply follow the instructions provided by the
bot. You will only need to do this once across all repositories using
our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct][coc]. For
more information see the [Code of Conduct FAQ][coc_faq] or contact
<opencode@microsoft.com> with any additional questions or comments.

<!-- LINKS -->
[cg]: https://github.com/Azure/azure-sdk-for-net/blob/Azure.ResourceManager.AppService_1.0.0-beta.4/sdk/resourcemanager/Azure.ResourceManager/docs/CONTRIBUTING.md
[coc]: https://opensource.microsoft.com/codeofconduct/
[coc_faq]: https://opensource.microsoft.com/codeofconduct/faq/

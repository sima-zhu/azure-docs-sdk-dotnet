---
title: Azure DataBox SDK for .NET
description: Reference for Azure DataBox SDK for .NET
author: pallavit
ms.author: pallavit
ms.data: 11/30/2022
ms.topic: reference
ms.devlang: dotnet
ms.service: databox
ms.date: 06/29/2021
---
# Azure Data Box APIs for .NET

## Overview

Create and manage Azure Data Box orders from your .NET applications with [Azure Data Box](https://docs.microsoft.com/en-us/azure/databox/).

## Management APIs

Create and manage Azure Data Box orders

Install the [NuGet package](https://www.nuget.org/packages/Microsoft.Azure.Management.DataBox) directly from the Visual Studio [Package Manager console](https://docs.microsoft.com/nuget/tools/package-manager-console) or with the [.NET Core CLI](https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package).

#### Visual Studio Package Manager

```powershell
Install-Package Microsoft.Azure.Management.Databox
```

```dotnetcli
dotnet add package Microsoft.Azure.Management.Databox
```

### Code Example

The following example gets a Data Box order.

```csharp
/* Include this "using" directive...
using Microsoft.Azure.Management.Databox
*/

using (DataBoxManagementClient client = new DataBoxManagementClient(
    new TokenCloudCredentials(subscriptionId, accessToken)))
{
    JobResource job = client.Jobs.Get(resourceGroupName, jobName);
}
```

> [!div class="nextstepaction"]
> [Explore the management APIs](https://docs.microsoft.com/en-us/dotnet/api/overview/azure/databox?view=azure-dotnet)
---
title: Azure Redis Cache SDK for .NET
description: Reference for Azure Redis Cache SDK for .NET
author: pallavit
ms.author: pallavit
ms.data: 01/05/2023
ms.topic: reference
ms.devlang: dotnet
ms.service: rediscache
ms.date: 10/19/2017
---
# Azure Cache for Redis libraries for .NET

## Overview

Azure Cache for Redis is a secure data cache and messaging broker that provides high throughput and low-latency access to data for applications.  For more information, see [How to Use Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache).

## Client library

Azure Cache for Redis is compatible with any Redis client API, including `StackExchange.Redis`.

Install the [NuGet package](https://www.nuget.org/packages/StackExchange.Redis) directly from the Visual Studio [Package Manager console][PackageManager] or with the [.NET Core CLI][DotNetCLI].

#### Visual Studio Package Manager

```powershell
Install-Package StackExchange.Redis
```

```dotnetcli
dotnet add package StackExchange.Redis
```

### Example

This example connects to a Azure Cache for Redis database instance, adds some strings to the cache by name, and then retrieves them again.

```csharp
/* Include this "using" directive.
using StackExchange.Redis;
*/

ConnectionMultiplexer connection = 
    ConnectionMultiplexer.Connect("contoso.redis.cache.windows.net,abortConnect=false,ssl=true,password=...");
    IDatabase cache = connection.GetDatabase();

// Perform cache operations using the cache object...
// Simple put of integral data types into the cache
cache.StringSet("key1", "value");
cache.StringSet("key2", 25);

// Simple get of data types from the cache
string key1 = cache.StringGet("key1");
int key2 = (int)cache.StringGet("key2");
```

## Management library

The Azure Cache for Redis management library allows you to manage Azure Cache for Redis resources and access keys.

Install the [NuGet package](https://www.nuget.org/packages/Microsoft.Azure.Management.Redis.Fluent) directly from the Visual Studio [Package Manager console][PackageManager] or with the [.NET Core CLI][DotNetCLI].

#### Visual Studio Package Manager

```powershell
Install-Package Microsoft.Azure.Management.Redis.Fluent
```

```dotnetcli
dotnet add package Microsoft.Azure.Management.Redis.Fluent
```

### Example

This example creates a new Azure Cache for Redis.

```csharp
/* Include these "using" directives...
using Microsoft.Azure.Management.ResourceManager.Fluent.Core;
using Microsoft.Azure.Management.Redis.Fluent;
*/

IRedisCache redisCache1 = azure.RedisCaches.Define("RedisCacheName")
    .WithRegion(Region.USCentral)
    .WithNewResourceGroup("ResourceGroupName")
    .WithBasicSku()
    .Create();
```

> [!div class="nextstepaction"]
> [Explore the management APIs](/dotnet/api/overview/azure/azurecacheforredis/management)


## Samples

* [Getting Started with Redis - Manage Redis - in .NET](https://github.com/Azure-Samples/redis-cache-dotnet-manage-cache)

[PackageManager]: https://docs.microsoft.com/nuget/tools/package-manager-console
[DotNetCLI]: https://docs.microsoft.com/dotnet/core/tools/dotnet-add-package
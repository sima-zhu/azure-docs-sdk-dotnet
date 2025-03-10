---
title: Azure Monitor Exporter client library for .NET
keywords: Azure, dotnet, SDK, API, Azure.Monitor.OpenTelemetry.Exporter, monitor
author: SameergMS
ms.author: sameerg
ms.date: 01/09/2023
ms.topic: reference
ms.devlang: dotnet
ms.service: monitor
---
# Azure Monitor Exporter client library for .NET - version 1.0.0-beta.6 




The [OpenTelemetry .NET](https://github.com/open-telemetry/opentelemetry-dotnet) exporters which send [telemetry data](/azure/azure-monitor/app/data-model) to [Azure Monitor](/azure/azure-monitor/app/app-insights-overview) following the [OpenTelemetry Specification](https://github.com/open-telemetry/opentelemetry-specification).

## Getting started

### Prerequisites

- **Azure Subscription:**  To use Azure services, including Azure Monitor Exporter for [OpenTelemetry .NET](https://github.com/open-telemetry/opentelemetry-dotnet), you'll need a subscription.  If you do not have an existing Azure account, you may sign up for a [free trial](https://azure.microsoft.com/free/dotnet/) or use your [Visual Studio Subscription](https://visualstudio.microsoft.com/subscriptions/) benefits when you [create an account](https://account.windowsazure.com/Home/Index).
- **Azure Application Insights Connection String:** To send telemetry data to the monitoring service you'll need connection string from Azure Application Insights. If you are not familiar with creating Azure resources, you may wish to follow the step-by-step guide for [Create an Application Insights resource](/azure/azure-monitor/app/create-new-resource) and [copy the connection string](/azure/azure-monitor/app/sdk-connection-string?tabs=net#find-your-connection-string).

### Install the package

#### Latest Version: [![Nuget](https://img.shields.io/nuget/vpre/Azure.Monitor.OpenTelemetry.Exporter.svg)](https://www.nuget.org/packages/Azure.Monitor.OpenTelemetry.Exporter/)  

Install the Azure Monitor Exporter for OpenTelemetry .NET with [NuGet](https://www.nuget.org/):
```dotnetcli
dotnet add package Azure.Monitor.OpenTelemetry.Exporter --prerelease
```

#### Nightly builds

Nightly builds are available from this repo's [dev feed](https://github.com/Azure/azure-sdk-for-net/blob/Azure.Monitor.OpenTelemetry.Exporter_1.0.0-beta.6/CONTRIBUTING.md#nuget-package-dev-feed).
These are provided without support and are not intended for production workloads.

### Add the Exporter

The following examples demonstrate how to add the `AzureMonitorExporter` to your OpenTelemetry configuration.

- Traces
    ```csharp
    Sdk.CreateTracerProviderBuilder()
        .AddAzureMonitorTraceExporter(o => o.ConnectionString = "InstrumentationKey=00000000-0000-0000-0000-000000000000")
        .Build();
    ```

  For a complete example see [TraceDemo.cs](https://github.com/Azure/azure-sdk-for-net/blob/Azure.Monitor.OpenTelemetry.Exporter_1.0.0-beta.6/sdk/monitor/Azure.Monitor.OpenTelemetry.Exporter/tests/Azure.Monitor.OpenTelemetry.Exporter.Demo/Traces/TraceDemo.cs).

- Metrics
    ```csharp
    Sdk.CreateMeterProviderBuilder()
        .AddAzureMonitorMetricExporter(o => o.ConnectionString = "InstrumentationKey=00000000-0000-0000-0000-000000000000")
        .Build();
    ```

  For a complete example see [MetricDemo.cs](https://github.com/Azure/azure-sdk-for-net/blob/Azure.Monitor.OpenTelemetry.Exporter_1.0.0-beta.6/sdk/monitor/Azure.Monitor.OpenTelemetry.Exporter/tests/Azure.Monitor.OpenTelemetry.Exporter.Demo/Metrics/MetricDemo.cs).

- Logs
    ```csharp
    LoggerFactory.Create(builder =>
    {
        builder.AddOpenTelemetry(options =>
        {
            options.AddAzureMonitorLogExporter(o => o.ConnectionString = "InstrumentationKey=00000000-0000-0000-0000-000000000000");
        });
    });
    ```

  For a complete example see [LogDemo.cs](https://github.com/Azure/azure-sdk-for-net/blob/Azure.Monitor.OpenTelemetry.Exporter_1.0.0-beta.6/sdk/monitor/Azure.Monitor.OpenTelemetry.Exporter/tests/Azure.Monitor.OpenTelemetry.Exporter.Demo/Logs/LogDemo.cs).

### Authenticate the client

Exporter does not use authentication. 

## Key concepts

Some key concepts for .NET include:

- [Overview of .NET distributed tracing](https://learn.microsoft.com/dotnet/core/diagnostics/distributed-tracing): 
  Distributed tracing is a diagnostic technique that helps engineers localize failures and performance issues within applications, especially those that may be distributed across multiple machines or processes. 

- [Overview of Logging in .NET](https://learn.microsoft.com/dotnet/core/extensions/logging): 
  .NET supports a logging API that works with a variety of built-in and third-party logging providers.

Some key concepts for Azure Monitor include:

- [IP Addresses used by Azure Monitor](/azure/azure-monitor/app/ip-addresses#outgoing-ports):
  This exporter sends traces to the configured Azure Monitor Resource using HTTPS.
  You might need to know IP addresses if the app or infrastructure that you're monitoring is hosted behind a firewall.

Some key concepts for OpenTelemetry include:

- [OpenTelemetry](https://opentelemetry.io/):
  OpenTelemetry is a set of libraries used to collect and export telemetry data
  (metrics, logs, and traces) for analysis in order to understand your software's performance and behavior.

- [Instrumentation](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/overview.md#instrumentation-libraries):
  The ability to call the OpenTelemetry API directly by any application is
  facilitated by instrumentation. A library that enables OpenTelemetry observability for another library is called an Instrumentation Library.

- [Tracing Signal](https://github.com/open-telemetry/opentelemetry-specification/blob/main/specification/overview.md#tracing-signal): 
  Trace refers to distributed tracing. It can be thought of as a directed acyclic graph (DAG) of Spans, where the edges between Spans are defined as parent/child relationship.

- [Sampling](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/trace/sdk.md#sampling): 
  Sampling is a mechanism to control the noise and overhead introduced by OpenTelemetry by reducing the number of samples of traces collected and sent to the backend.

- [Metric Signal](https://github.com/open-telemetry/opentelemetry-specification/blob/main/specification/overview.md#metric-signal):
  OpenTelemetry allows to record raw measurements or metrics with predefined aggregation and a set of attributes (dimensions).

- [Log Signal](https://github.com/open-telemetry/opentelemetry-specification/blob/main/specification/overview.md#log-signal):
  A recording of an event. Typically the record includes a timestamp indicating when the event happened as well as other data that describes what happened, where it happened, etc.

For more information on the OpenTelemetry project, please review the [OpenTelemetry Specifications](https://github.com/open-telemetry/opentelemetry-specification).

## Examples

Refer to [`Program.cs`](https://github.com/Azure/azure-sdk-for-net/blob/Azure.Monitor.OpenTelemetry.Exporter_1.0.0-beta.6/sdk/monitor/Azure.Monitor.OpenTelemetry.Exporter/tests/Azure.Monitor.OpenTelemetry.Exporter.Demo/Program.cs) for a complete demo.

## Troubleshooting

The Azure Monitor exporter uses EventSource for its own internal logging. The exporter logs are available to any EventListener by opting into the source named "OpenTelemetry-AzureMonitor-Exporter".

## Next steps

For more information on Azure SDK, please refer to [this website](https://azure.github.io/azure-sdk/)

## Contributing

See [CONTRIBUTING.md](https://github.com/Azure/azure-sdk-for-net/blob/Azure.Monitor.OpenTelemetry.Exporter_1.0.0-beta.6/CONTRIBUTING.md) for details on contribution process.

## Release Schedule

This exporter is under active development.

The library is not yet _generally available_, and is not officially supported. Future releases will not attempt to maintain backwards compatibility with previous releases. Each beta release includes significant changes to the exporter package, making them incompatible with each other.


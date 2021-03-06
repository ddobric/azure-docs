---
title: Get Started with Event Hubs with C and Apache Storm | Microsoft Docs
description: Follow this tutorial to get started using Azure Event Hubs; sending events in C and receiving them in an Apache Storm cluster.
services: event-hubs
documentationcenter: ''
author: jtaubensee
manager: timlt
editor: ''

ms.assetid: 3b15825e-c53c-471b-870c-686bff46885a
ms.service: event-hubs
ms.workload: na
ms.tgt_pltfrm: c
ms.devlang: java
ms.topic: article
ms.date: 11/30/2016
ms.author: jotaub;sethm

---
# Get started with Event Hubs
[!INCLUDE [service-bus-selector-get-started](../../includes/service-bus-selector-get-started.md)]

## Introduction
Event Hubs is a highly scalable ingestion system that can intake millions of events per second, enabling an application to process and analyze the massive amounts of data produced by your connected devices and applications. Once collected into Event Hubs, you can transform and store data using any real-time analytics provider or storage cluster.

For more information, please see [Event Hubs overview].

In this tutorial, you will learn how to ingest messages into an Event Hub using a console application in C, and to retrieve them in parallel using Apache Storm.

To complete this tutorial, you will need the following:

* A C development environment. For this tutorial, we will assume the gcc stack on an [Azure Linux VM](../virtual-machines/virtual-machines-linux-quick-create-cli.md?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json) with Ubuntu 14.04. Instructions for other environments will be provided in external links.
* A Java development environment configured to run [Maven](http://maven.apache.org/). For this tutorial, we will assume [Eclipse](https://www.eclipse.org/).
* An active Azure account. If you don't have an account, you can create a free account in just a couple of minutes. For details, see [Azure Free Trial](https://azure.microsoft.com/pricing/free-trial/).

[!INCLUDE [event-hubs-create-event-hub](../../includes/event-hubs-create-event-hub.md)]

[!INCLUDE [service-bus-event-hubs-get-started-send-c](../../includes/service-bus-event-hubs-get-started-send-c.md)]

[!INCLUDE [service-bus-event-hubs-get-started-receive-storm](../../includes/service-bus-event-hubs-get-started-receive-storm.md)]

## Run the applications
Now you are ready to run the applications.

1. Run the **LogTopology** class from Eclipse, then wait for it to start the receivers for all the partitions.
2. Run the **sender** program, and see the events appear in the receiver window.
   
   ![][23]

> [!NOTE]
> In this tutorial only, use Storm in local mode for development purposes. Refer to the [HDInsight Storm overview] and the official [Apache Storm] documentation for more information of Storm deployments and patterns.

## Next steps
The following resources are available for developing applications integrating Event Hubs and Storm.

* [Analyzing sensor data with Storm and HDInsight][Analyzing sensor data with Storm and HDInsight] is a full scenario tutorial using Event Hubs, Storm, and HBase to ingest sensor data in a Hadoop cluster.
* [Develop streaming data processing applications with SCP.NET and C# on Storm and HDInsight][Develop streaming data processing applications with SCP.NET and C# on Storm and HDInsight] is a tutorial on how to write Storm pipelines using C#.

<!-- Images. -->
[23]: ./media/event-hubs-c-storm-getstarted/receive-storm3.png

<!-- Links -->
[Azure classic portal]: https://manage.windowsazure.com/
[Event Processor Host]: https://www.nuget.org/packages/Microsoft.Azure.ServiceBus.EventProcessorHost
[Event Hubs overview]: event-hubs-overview.md

[Apache Storm]: https://storm.incubator.apache.org
[HDInsight Storm overview]: ../hdinsight/hdinsight-storm-overview.md
[Analyzing sensor data with Storm and HDInsight]: ../hdinsight/hdinsight-storm-sensor-data-analysis.md
[Develop streaming data processing applications with SCP.NET and C# on Storm and HDInsight]: ../hdinsight/hdinsight-storm-develop-csharp-visual-studio-topology.md

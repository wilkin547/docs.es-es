---
title: Conexión de .NET para Apache Spark a Azure Event Hubs
description: Obtenga información sobre cómo conectarse a Azure Event Hubs desde la instancia local de .NET para Apache Spark.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 4de4836ba2b63429e29ae819afac09c7a3998480
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91954976"
---
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a><span data-ttu-id="0f26f-103">Conexión de .NET para Apache Spark a Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="0f26f-103">Connect .NET for Apache Spark to Azure Event Hubs</span></span>

<span data-ttu-id="0f26f-104">En este artículo, obtendrá información sobre cómo conectar la aplicación [.NET para Apache Spark](https://github.com/dotnet/spark) con Azure Event Hubs para leer y escribir flujos de Apache Kafka.</span><span class="sxs-lookup"><span data-stu-id="0f26f-104">In this article, you will learn how to connect your [.NET for Apache Spark](https://github.com/dotnet/spark) application with Azure Event Hubs to read and write Apache Kafka streams.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f26f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f26f-105">Prerequisites</span></span>

<span data-ttu-id="0f26f-106">Tener un espacio de nombres de Event Hubs listo con un centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="0f26f-106">Have an Event Hubs Namespace ready with an event hub.</span></span> <span data-ttu-id="0f26f-107">Para obtener una guía paso a paso, vea [Inicio rápido: Creación de un centro de eventos mediante Azure Portal](/azure/event-hubs/event-hubs-create).</span><span class="sxs-lookup"><span data-stu-id="0f26f-107">For a step-by-step guide, refer to [Quickstart: Create an event hub using Azure portal](/azure/event-hubs/event-hubs-create).</span></span> <span data-ttu-id="0f26f-108">Asegúrese de seleccionar el plan de tarifa Estándar al crear el espacio de nombres del centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="0f26f-108">Make sure to select the Standard Pricing tier while creating the Event Hub Namespace.</span></span>

## <a name="what-is-azure-event-hubs"></a><span data-ttu-id="0f26f-109">¿Qué es Azure Event Hubs?</span><span class="sxs-lookup"><span data-stu-id="0f26f-109">What is Azure Event Hubs</span></span>

<span data-ttu-id="0f26f-110">[Azure Event Hubs](/azure/event-hubs/event-hubs-about) es una plataforma de streaming de macrodatos y un servicio de ingesta de eventos.</span><span class="sxs-lookup"><span data-stu-id="0f26f-110">[Azure Event Hubs](/azure/event-hubs/event-hubs-about) is a big-data streaming platform and event-ingestion service.</span></span> <span data-ttu-id="0f26f-111">Es una plataforma como servicio (PaaS) totalmente administrada que se puede integrar fácilmente con [Apache Kafka](https://kafka.apache.org/) para proporcionarle la experiencia de Kafka de PaaS sin tener que administrar, configurar o ejecutar clústeres propios.</span><span class="sxs-lookup"><span data-stu-id="0f26f-111">It is a fully managed Platform-as-a-Service (PaaS) that can easily integrate with [Apache Kafka](https://kafka.apache.org/) to give you the PaaS Kafka experience without having to manage, configure, or run your own clusters.</span></span>

## <a name="connect-your-application-to-azure-event-hubs"></a><span data-ttu-id="0f26f-112">Conexión de la aplicación a Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="0f26f-112">Connect your application to Azure Event Hubs</span></span>

1. <span data-ttu-id="0f26f-113">Obtenga la cadena de conexión de Event Hubs y el nombre de dominio completo (FQDN) para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="0f26f-113">Get the Event Hubs connection string and fully qualified domain name (FQDN) for later use.</span></span> <span data-ttu-id="0f26f-114">Para obtener instrucciones, consulte [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string) (Obtención de una cadena de conexión de Event Hubs).</span><span class="sxs-lookup"><span data-stu-id="0f26f-114">For instructions, see [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string).</span></span>
2. <span data-ttu-id="0f26f-115">Establezca las configuraciones siguientes con detalles del espacio de nombres en el código para empezar a leer desde Event Hubs para Kafka:</span><span class="sxs-lookup"><span data-stu-id="0f26f-115">Set the following configurations with details from your namespace in your code to start reading from Event Hubs for Kafka:</span></span>
    1. <span data-ttu-id="0f26f-116">En la aplicación, actualice **BOOTSTRAP_SERVERS** y **EH_SASL** de esta forma:</span><span class="sxs-lookup"><span data-stu-id="0f26f-116">Update **BOOTSTRAP_SERVERS** and **EH_SASL** in your application like so:</span></span>

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a><span data-ttu-id="0f26f-117">Lectura desde un flujo de Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="0f26f-117">Read from Azure Event Hub stream</span></span>

<span data-ttu-id="0f26f-118">Ahora puede iniciar el streaming con Event Hubs como lo haría con Kafka.</span><span class="sxs-lookup"><span data-stu-id="0f26f-118">You can now start streaming with Event Hubs as you would with Kafka.</span></span> <span data-ttu-id="0f26f-119">El código de ejemplo se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="0f26f-119">Sample code as shown below:</span></span>

```csharp
SparkSession spark = SparkSession
    .Builder()
    .AppName("Connect Event Hub")
    .GetOrCreate();

DataFrame df = spark
    .ReadStream()
    .Format("kafka")
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("subscribe", "spark-test")
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("kafka.request.timeout.ms", "60000")
    .Option("kafka.session.timeout.ms", "60000")
    .Option("failOnDataLoss", "false")
    .Load();

DataFrame dfWrite = df
    .WriteStream()
    .OutputMode("append")
    .Format("console")
    .Start();
```

## <a name="write-to-azure-event-hub-stream"></a><span data-ttu-id="0f26f-120">Escritura en un flujo de Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="0f26f-120">Write to Azure Event Hub stream</span></span>

<span data-ttu-id="0f26f-121">También puede escribir en Event Hubs de la misma manera, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="0f26f-121">You can also write to Event Hubs in the same way, as shown below:</span></span>

```csharp
// df is the DataFrame to write

df.WriteStream()
    .Format("kafka")
    .Option("topic", topics)
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("checkpointLocation", "./checkpoint")
    .Start();
```

## <a name="run-your-application"></a><span data-ttu-id="0f26f-122">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0f26f-122">Run your application</span></span>

<span data-ttu-id="0f26f-123">A fin de ejecutar la aplicación .NET para Apache Spark, defina el módulo `spark-sql-kafka-0-10` como parte de la definición de compilación en el proyecto de Spark, con `libraryDependency` en `build.sbt` para los proyectos de sbt.</span><span class="sxs-lookup"><span data-stu-id="0f26f-123">In order to run your .NET for Apache Spark application, define the `spark-sql-kafka-0-10` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="0f26f-124">Para entornos de Spark como `spark-submit` (o `spark-shell`), use la opción de línea de comandos `--packages` de esta forma:</span><span class="sxs-lookup"><span data-stu-id="0f26f-124">For Spark environments such as `spark-submit` (or `spark-shell`), use the `--packages` command-line option like so:</span></span>

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> <span data-ttu-id="0f26f-125">Asegúrese de incluir la versión del paquete correspondiente a la versión de Spark que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="0f26f-125">Make sure to include the package version in accordance with the version of Spark being run.</span></span>

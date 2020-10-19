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
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a>Conexión de .NET para Apache Spark a Azure Event Hubs

En este artículo, obtendrá información sobre cómo conectar la aplicación [.NET para Apache Spark](https://github.com/dotnet/spark) con Azure Event Hubs para leer y escribir flujos de Apache Kafka.

## <a name="prerequisites"></a>Requisitos previos

Tener un espacio de nombres de Event Hubs listo con un centro de eventos. Para obtener una guía paso a paso, vea [Inicio rápido: Creación de un centro de eventos mediante Azure Portal](/azure/event-hubs/event-hubs-create). Asegúrese de seleccionar el plan de tarifa Estándar al crear el espacio de nombres del centro de eventos.

## <a name="what-is-azure-event-hubs"></a>¿Qué es Azure Event Hubs?

[Azure Event Hubs](/azure/event-hubs/event-hubs-about) es una plataforma de streaming de macrodatos y un servicio de ingesta de eventos. Es una plataforma como servicio (PaaS) totalmente administrada que se puede integrar fácilmente con [Apache Kafka](https://kafka.apache.org/) para proporcionarle la experiencia de Kafka de PaaS sin tener que administrar, configurar o ejecutar clústeres propios.

## <a name="connect-your-application-to-azure-event-hubs"></a>Conexión de la aplicación a Azure Event Hubs

1. Obtenga la cadena de conexión de Event Hubs y el nombre de dominio completo (FQDN) para su uso posterior. Para obtener instrucciones, consulte [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string) (Obtención de una cadena de conexión de Event Hubs).
2. Establezca las configuraciones siguientes con detalles del espacio de nombres en el código para empezar a leer desde Event Hubs para Kafka:
    1. En la aplicación, actualice **BOOTSTRAP_SERVERS** y **EH_SASL** de esta forma:

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a>Lectura desde un flujo de Azure Event Hubs

Ahora puede iniciar el streaming con Event Hubs como lo haría con Kafka. El código de ejemplo se muestra a continuación:

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

## <a name="write-to-azure-event-hub-stream"></a>Escritura en un flujo de Azure Event Hubs

También puede escribir en Event Hubs de la misma manera, como se muestra a continuación:

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

## <a name="run-your-application"></a>Ejecución de la aplicación

A fin de ejecutar la aplicación .NET para Apache Spark, defina el módulo `spark-sql-kafka-0-10` como parte de la definición de compilación en el proyecto de Spark, con `libraryDependency` en `build.sbt` para los proyectos de sbt. Para entornos de Spark como `spark-submit` (o `spark-shell`), use la opción de línea de comandos `--packages` de esta forma:

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> Asegúrese de incluir la versión del paquete correspondiente a la versión de Spark que se ejecuta.

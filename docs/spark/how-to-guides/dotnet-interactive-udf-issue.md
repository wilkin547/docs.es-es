---
title: Escritura y llamada a UDF en entornos interactivos de .NET para Apache Spark
description: Obtenga información sobre cómo escribir y llamar a UDF en shells interactivos de .NET para Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: c29c3a9f6269a342d1051d6d979a4e3adb42da02
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875556"
---
# <a name="write-and-call-udfs-in-net-for-apache-spark-interactive-environments"></a>Escritura y llamada a UDF en entornos interactivos de .NET para Apache Spark

En este artículo, aprenderá a usar funciones definidas por el usuario (UDF) en un entorno interactivo de .NET para Apache Spark.

## <a name="prerequisites"></a>Requisitos previos

1. Instalar [.NET Interactive](https://github.com/dotnet/interactive)
2. Instalar [Jupyter Lab](https://jupyter.org/)

## <a name="net-for-apache-spark-interactive-experience"></a>Experiencia interactiva de .NET para Apache Spark

[.NET para Apache Spark](https://github.com/dotnet/spark) usa [.NET Interactive](https://devblogs.microsoft.com/dotnet/net-interactive-is-here-net-notebooks-preview-2/) a fin de proporcionar compatibilidad con .NET para la experiencia interactiva en Spark. Para saber cómo configurar el entorno a fin de probar .NET Interactive con cuadernos de Jupyter Notebook, vea el [repositorio de .NET Interactive](https://github.com/dotnet/interactive).

Además, se recomienda repasar [este artículo sobre la serialización de UDF en .NET para Apache Spark](udf-guide.md) a fin de entender qué son las UDF y cómo se serializan en .NET para Apache Spark.
En esta guía se usan cuadernos de Jupyter Notebook para ilustrar cómo usar las UDF en una experiencia interactiva.

## <a name="define-a-udf-in-net-interactive"></a>Definición de una UDF en .NET Interactive

En la experiencia interactiva, una celda se puede considerar el fragmento de código que se envía como parte de una iteración de [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop). Por ejemplo, examine el cuaderno siguiente para entender lo que significa:

![Celdas de Jupyter Notebook](./media/dotnet-interactive/dotnet-interactive-cells.png)

Cada uno de los bloques marcados con la flecha roja es una celda o un envío de código a Spark. Ahora, al definir una UDF que hace referencia a un objeto personalizado definido por el usuario, es necesario hacerlo en la misma celda en la que se define el objeto al que hace referencia. En este ejemplo puede comprobar el aspecto que tiene:

![UDF funcional](./media/dotnet-interactive/working-udf.png)

## <a name="call-a-udf-on-a-dataframe"></a>Llamada a una UDF en un objeto DataFrame

Cuando se llama a una UDF definida previamente en un objeto `DataFrame`, es importante asegurarse de que la UDF se define en una celda enviada con anterioridad, antes de llamarla, como se puede observar en el ejemplo anterior.

Ahora se verá lo que sucede si se llama a la UDF en la misma celda en la que está definida.

![Error en la llamada a la UDF](./media/dotnet-interactive/udf_fails.png)

El error resaltado anteriormente se debe a que primero se deben compilar los ensamblados de UDF y enviarse a los trabajos antes de que se pueda llamar en un objeto DataFrame.

Estos son algunos aspectos importantes que tener en cuenta al implementar las UDF en la experiencia interactiva de .NET para Apache Spark (como los [cuadernos de Azure Synapse](/azure/synapse-analytics/spark/apache-spark-development-using-notebooks)).

## <a name="faqs"></a>Preguntas más frecuentes

1. **¿Por qué la UDF que hace referencia a un objeto definido por el usuario personalizado produce el error `Type Submission#_ is not marked as serializable`?**
    .NET Interactive encapsula cada una de estas celdas con una clase contenedora del número de envío de la celda, para identificar de forma única cada celda que se envía. Como se explica con detalle en [esta guía](udf-guide.md), cuando se serializa una UDF que hace referencia a un objeto personalizado, su destino también se selecciona para la serialización, que en el caso de .NET Interactive se encapsula mediante la clase contenedora de la celda en la que se define el objeto personalizado.
    Ahora se verá cómo afecta eso a la definición de la UDF en el cuaderno:

    ![Error de serialización de la UDF](./media/dotnet-interactive/udf-serialization-error.png)

    Como se aprecia en el caso de `udf2_fails`, se ve el mensaje de error que indica que el tipo `Submission#7` no está marcado como serializable; esto se debe a que .NET Interactive encapsula todos los objetos definidos en una celda con su clase `Submission#`, que se genera sobre la marcha y, por tanto, no se marca como `Serializable`.

    Por este motivo, es **obligatorio que una UDF que hace referencia a un objeto personalizado se defina en la misma celda que ese objeto**.

2. **¿Por qué no funcionan las variables de difusión con .NET Interactive?**
    Por los motivos explicados anteriormente, las variables de difusión no funcionan con .NET Interactive. Es aconsejable repasar [esta guía sobre las variables de difusión](broadcast-guide.md) para comprender mejor qué son y cómo usarlas. El motivo por el que las variables de difusión no funcionan con escenarios interactivos se debe al diseño de .NET Interactive de anexar cada objeto definido en una celda con su clase de envío de celda; al no estar marcada como serializable, se inicia la misma excepción que se ha mostrado antes.
    Ahora se profundizará con el ejemplo siguiente:

    ![Error de las variables de difusión](./media/dotnet-interactive/broadcast-fails.png)

    Como se ha recomendado en las secciones anteriores, la UDF y el objeto al que hace referencia (en este caso la variable de difusión) se definen en la misma celda, pero todavía se ve que el error `SerializationException` se queja de que `Microsoft.Spark.Sql.Session` no se marque como serializable. El motivo es que cuando el compilador intenta serializar el objeto de variable de difusión `bv`, encuentra que al nombre se le anexa el objeto `spark` [`SparkSession`](https://github.com/dotnet/spark/blob/main/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20), que se debe marcar como serializable. Esto se puede mostrar con más facilidad al examinar el ensamblado descompilado de este envío de celda:

    ![Código de ensamblado descompilado](./media/dotnet-interactive/decompiledAssembly.png)

    Si la clase [`SparkSession`](https://github.com/dotnet/spark/blob/main/src/csharp/Microsoft.Spark/Sql/SparkSession.cs#L20) se marca como `[Serializable]`, se puede conseguir que funcione, pero no es una solución ideal, ya que no interesa permitir al usuario serializar un objeto SparkSession, lo que podría dar lugar a un comportamiento extraño e indeseable. Este es un [problema conocido](https://github.com/dotnet/spark/issues/619) y se resolverá en versiones futuras.

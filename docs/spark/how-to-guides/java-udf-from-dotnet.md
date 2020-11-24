---
title: Invocación de UDF de Java desde la aplicación .NET para Apache Spark
description: Obtenga información sobre cómo invocar UDF de Java desde una aplicación .NET para Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 17f0ff611e68a5dab2032f78ef75912f314d88a5
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688272"
---
# <a name="call-a-java-udf-from-your-net-for-apache-spark-application"></a><span data-ttu-id="58f1d-103">Invocación de una UDF de Java desde la aplicación .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="58f1d-103">Call a Java UDF from your .NET for Apache Spark application</span></span>

<span data-ttu-id="58f1d-104">En este artículo, obtendrá información sobre cómo invocar una función definida por el usuario (UDF) de Java desde la aplicación [.NET para Apache Spark](https://github.com/dotnet/spark).</span><span class="sxs-lookup"><span data-stu-id="58f1d-104">In this article, you learn how to call a Java User-Defined Function (UDF) from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

1. <span data-ttu-id="58f1d-105">Procedimiento para definir las UDF de Java y compilarlas en un archivo jar: este paso no es necesario si ya tiene una UDF definida en un archivo jar.</span><span class="sxs-lookup"><span data-stu-id="58f1d-105">How to define your Java UDFs and compile them into a jar - this step is not needed if you already have a UDF defined in a jar file.</span></span> <span data-ttu-id="58f1d-106">En ese caso, lo único que necesita es el nombre completo de la UDF, incluido el paquete.</span><span class="sxs-lookup"><span data-stu-id="58f1d-106">In which case, all you need is the full name of the UDF function including the package.</span></span>
2. <span data-ttu-id="58f1d-107">Registre y llame a la UDF de Java en la aplicación .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="58f1d-107">Register and call your Java UDF in your .NET for Apache Spark application.</span></span>

## <a name="define-and-compile-your-java-udfs"></a><span data-ttu-id="58f1d-108">Definición y compilación de las UDF de Java</span><span class="sxs-lookup"><span data-stu-id="58f1d-108">Define and compile your Java UDFs</span></span>

1. <span data-ttu-id="58f1d-109">Cree un proyecto de Maven o SBT, y agregue las dependencias siguientes al archivo de configuración del proyecto:</span><span class="sxs-lookup"><span data-stu-id="58f1d-109">Create a Maven or SBT project and add the following dependencies into the project configuration file:</span></span>
    1. `org.apache.spark.spark-core_2.11.<version>`
    2. `org.apache.spark.spark-sql_2.11.<version>`
2. <span data-ttu-id="58f1d-110">Para definir la UDF de Java, implemente la [interfaz adecuada](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) (en función de la signatura de la UDF) e importe el paquete correspondiente, como se muestra a continuación en un ejemplo sencillo.</span><span class="sxs-lookup"><span data-stu-id="58f1d-110">Define your Java UDF by implementing the [relevant interface](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) (according to your UDF's signature) and importing the relevant package as shown below in a simple example</span></span>

    ```java
    package com.ScalaUdf.app; // Name of package where UDF is defined
    import org.apache.spark.sql.api.java.UDF1; // UDF interface to implement

    public class JavaUdf implements UDF1<Integer, Integer> { // Name of the Java UDF
        private static final int serialVersionUID = 1;
        @Override
        public Integer call(Integer num) throws Exception { // Define logic of UDF
            return (num + 5);
        }
    }
    ```

3. <span data-ttu-id="58f1d-111">Compile y empaquete el proyecto para crear un archivo ejecutable jar, por ejemplo `UdfApp-0.0.1.jar`.</span><span class="sxs-lookup"><span data-stu-id="58f1d-111">Compile and package your project to create and executable jar say `UdfApp-0.0.1.jar`.</span></span>

## <a name="register-and-call-java-udfs-in-net-for-apache-spark"></a><span data-ttu-id="58f1d-112">Registro y llamada a UDF de Java en .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="58f1d-112">Register and call Java UDFs in .NET for Apache Spark</span></span>

1. <span data-ttu-id="58f1d-113">Use la API [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424) para registrar la UDF de Java con Spark SQL.</span><span class="sxs-lookup"><span data-stu-id="58f1d-113">Use the [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424) API to register your Java UDF with Spark SQL.</span></span>
2. <span data-ttu-id="58f1d-114">Registre el objeto `DataFrame` en el que quiera llamar a la UDF como una tabla SQL mediante la función [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982).</span><span class="sxs-lookup"><span data-stu-id="58f1d-114">Register the `DataFrame` on which you want to call your UDF as an SQL Table using the [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982) function.</span></span>
3. <span data-ttu-id="58f1d-115">Use `SparkSession.Sql` para llamar a la UDF en la vista de tabla con Spark SQL.</span><span class="sxs-lookup"><span data-stu-id="58f1d-115">Use `SparkSession.Sql` to call the UDF on the table view using Spark SQL.</span></span>
<span data-ttu-id="58f1d-116">Un ejemplo básico para ilustrar los pasos anteriores:</span><span class="sxs-lookup"><span data-stu-id="58f1d-116">A basic example to illustrate the above steps:</span></span>

    ```csharp
    class Program
    {
        static void Main()
        {
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Scala/Java UDFs from .NET for Apache Spark")
                .GetOrCreate();
            spark.Udf().RegisterJava<int>("udfAdd5", "com.ScalaUdf.app.JavaUdf"); // Register your Java UDF as 'udfAdd5'
            DataFrame df = spark.CreateDataFrame(new int[] { 2, 5 });
            df.CreateOrReplaceTempView("numbersData"); // Create an SQL table from the DataFrame `df`
            DataFrame dfUdf = spark.Sql("SELECT udfAdd5(_1) As Result FROM numbersData"); // Call the registered UDF on the table
            dfUdf.Show();
            spark.Stop();
        }
    }
    ```

4. <span data-ttu-id="58f1d-117">Para enviar esta aplicación mediante `spark-submit`, pase el archivo jar de la UDF de Java compilado previamente a través de la opción `--jars`:</span><span class="sxs-lookup"><span data-stu-id="58f1d-117">Submit this application using `spark-submit` by passing the previously compiled Java UDF jar through the `--jars` option:</span></span>

    ```bash
    spark-submit --master local --jars UdfApp-0.0.1.jar --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-2-4_2.11-1.0.0.jar InterRuntimeUDFs.exe
    ```

    <span data-ttu-id="58f1d-118">En el objeto DataFrame `dfUdf` resultante se ha agregado el número 5 a cada fila de la columna de entrada, tal y como se define en `JavaUdf`:</span><span class="sxs-lookup"><span data-stu-id="58f1d-118">The resultant `dfUdf` DataFrame had the number 5 added to each row of the input column as defined by `JavaUdf`:</span></span>

    ```text
    +-------+
    | Result|
    +-------+
    |      7|
    |     10|
    +-------+
    ```

## <a name="call-net-udf-from-scala-or-python-in-apache-spark"></a><span data-ttu-id="58f1d-119">Llamada a la UDF de .NET desde Scala o Python en Apache Spark</span><span class="sxs-lookup"><span data-stu-id="58f1d-119">Call .NET UDF from Scala or Python in Apache Spark</span></span>

<span data-ttu-id="58f1d-120">También puede registrar e invocar una UDF de C# desde una aplicación de Apache Spark escrita en Scala o Python mediante [la herramienta de código abierto sparkdotnetudf](https://github.com/imback82/sparkdotnetudf).</span><span class="sxs-lookup"><span data-stu-id="58f1d-120">You can also register and invoke a C# UDF from an Apache Spark application written in Scala or Python using [the sparkdotnetudf open source tool](https://github.com/imback82/sparkdotnetudf).</span></span>

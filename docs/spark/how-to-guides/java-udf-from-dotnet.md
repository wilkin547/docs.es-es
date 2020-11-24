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
# <a name="call-a-java-udf-from-your-net-for-apache-spark-application"></a>Invocación de una UDF de Java desde la aplicación .NET para Apache Spark

En este artículo, obtendrá información sobre cómo invocar una función definida por el usuario (UDF) de Java desde la aplicación [.NET para Apache Spark](https://github.com/dotnet/spark).

1. Procedimiento para definir las UDF de Java y compilarlas en un archivo jar: este paso no es necesario si ya tiene una UDF definida en un archivo jar. En ese caso, lo único que necesita es el nombre completo de la UDF, incluido el paquete.
2. Registre y llame a la UDF de Java en la aplicación .NET para Apache Spark.

## <a name="define-and-compile-your-java-udfs"></a>Definición y compilación de las UDF de Java

1. Cree un proyecto de Maven o SBT, y agregue las dependencias siguientes al archivo de configuración del proyecto:
    1. `org.apache.spark.spark-core_2.11.<version>`
    2. `org.apache.spark.spark-sql_2.11.<version>`
2. Para definir la UDF de Java, implemente la [interfaz adecuada](https://github.com/apache/spark/blob/master/sql/core/src/main/java/org/apache/spark/sql/api/java/UDF1.java) (en función de la signatura de la UDF) e importe el paquete correspondiente, como se muestra a continuación en un ejemplo sencillo.

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

3. Compile y empaquete el proyecto para crear un archivo ejecutable jar, por ejemplo `UdfApp-0.0.1.jar`.

## <a name="register-and-call-java-udfs-in-net-for-apache-spark"></a>Registro y llamada a UDF de Java en .NET para Apache Spark

1. Use la API [`RegisterJava`](https://github.com/dotnet/spark/blob/8dcdcdc7c60d5f42cba5a90f1346d854ab5bf7bb/src/csharp/Microsoft.Spark/Sql/UDFRegistration.cs#L424) para registrar la UDF de Java con Spark SQL.
2. Registre el objeto `DataFrame` en el que quiera llamar a la UDF como una tabla SQL mediante la función [`CreateOrReplaceTempView`](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L982).
3. Use `SparkSession.Sql` para llamar a la UDF en la vista de tabla con Spark SQL.
Un ejemplo básico para ilustrar los pasos anteriores:

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

4. Para enviar esta aplicación mediante `spark-submit`, pase el archivo jar de la UDF de Java compilado previamente a través de la opción `--jars`:

    ```bash
    spark-submit --master local --jars UdfApp-0.0.1.jar --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-2-4_2.11-1.0.0.jar InterRuntimeUDFs.exe
    ```

    En el objeto DataFrame `dfUdf` resultante se ha agregado el número 5 a cada fila de la columna de entrada, tal y como se define en `JavaUdf`:

    ```text
    +-------+
    | Result|
    +-------+
    |      7|
    |     10|
    +-------+
    ```

## <a name="call-net-udf-from-scala-or-python-in-apache-spark"></a>Llamada a la UDF de .NET desde Scala o Python en Apache Spark

También puede registrar e invocar una UDF de C# desde una aplicación de Apache Spark escrita en Scala o Python mediante [la herramienta de código abierto sparkdotnetudf](https://github.com/imback82/sparkdotnetudf).

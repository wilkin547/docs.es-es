---
title: Tutorial de procesamiento por lotes con .NET para Apache Spark
description: Aprenda a realizar el procesamiento por lotes con .NET para Apache Spark.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: 28674c583466bb4873581c9d233b9a508019b045
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876947"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a>Tutorial: Procesamiento por lotes con .NET para Apache Spark

En este tutorial, aprenderá a realizar el procesamiento por lotes con .NET para Apache Spark. El procesamiento por lotes es la transformación de datos en reposo, lo que significa que los datos de origen ya se han cargado en el almacenamiento de datos.

El procesamiento por lotes se realiza normalmente sobre grandes conjuntos de valores planos que se deben preparar para su posterior análisis. El procesamiento de registros y el almacenamiento de datos son escenarios comunes de procesamiento por lotes. En este escenario, se analiza la información sobre los proyectos de GitHub, como el número de veces que se han bifurcado proyectos diferentes o cómo de recientemente se han actualización los proyectos.

En este tutorial, aprenderá a:

> [!div class="checklist"]
>
> * Crear y ejecutar una aplicación de .NET para Apache Spark
> * Leer datos en DataFrame y prepararlos para su análisis
> * Procesar los datos mediante Spark SQL

## <a name="prerequisites"></a>Requisitos previos

Si esta es la primera vez que usa .NET para Apache Spark, consulte el tutorial [Introducción a .NET para Apache Spark](get-started.md) para aprender a preparar el entorno y ejecutar la primera aplicación .NET para Apache Spark.

## <a name="download-the-sample-data"></a>Descargar los datos de ejemplo

[GHTorrent](http://ghtorrent.org/) supervisa todos los eventos públicos de GitHub, como información sobre los proyectos, confirmaciones y monitores, y almacena los eventos y su estructura en bases de datos. Los datos recopilados en distintos períodos de tiempo están disponibles como archivos descargables. Dado que los archivos de volcado de memoria son muy grandes, en esta guía se usa una [versión truncada del archivo de volcado](https://github.com/dotnet/spark/tree/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) que se puede descargar desde GitHub.

> [!NOTE]
> El conjunto de datos de GHTorrent se distribuye con un esquema de licencia dual ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)). En el caso de usos no comerciales (por ejemplo, para educación, investigación o personales), el conjunto de datos se distribuye con la [licencia CC-BY-SA](https://creativecommons.org/licenses/by-sa/4.0/).

## <a name="create-a-console-application"></a>Creación de una aplicación de consola

1. En el símbolo del sistema, ejecute los comandos siguientes para crear una aplicación de consola:

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática. El parámetro `-o` crea un directorio llamado *mySparkBatchApp* donde se almacena la aplicación y lo rellena con los archivos necesarios. El comando `cd mySparkBatchApp` cambia el directorio al directorio de la aplicación que acaba de crear.

1. Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark. En la consola, ejecute el siguiente comando:

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a>Creación de una SparkSession

1. Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs* en *mySparkBatchApp*.

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. Agregue el código siguiente al espacio de nombres del proyecto. *s_referenceData* se usa más adelante en el programa para filtrar por la fecha.

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. Agregue el código siguiente dentro del método Main para establecer un nuevo objeto SparkSession. SparkSession es el punto de entrada para programar Spark con la API DataFrame y DataSet. Al llamar al objeto `spark`, puede acceder a la funcionalidad de Spark y DataFrame en todo el programa.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a>Preparación de los datos

1. Lea el archivo de entrada en un objeto `DataFrame`, que es una recopilación distribuida de datos organizados en columnas con nombre. Puede establecer las columnas para los datos mediante <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>. Use el método <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> para mostrar los datos en DataFrame. Asegúrese de actualizar la ruta de acceso del archivo CSV a la ubicación de los datos de GitHub que descargó.

   ```csharp
   DataFrame projectsDf = spark
       .Read()
       .Schema("id INT, url STRING, owner_id INT, " +
       "name STRING, descriptor STRING, language STRING, " +
       "created_at STRING, forked_from INT, deleted STRING" +
       "updated_at STRING")
       .Csv("filepath");

   projectsDf.Show();
   ```

1. Use el método <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> para colocar filas con valores NA (NULL) y el método <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> para quitar ciertas columnas de los datos. Esto ayuda a evitar errores si intenta analizar datos nulos o columnas que no son de interés para el análisis final.

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a>Análisis de los datos

Spark SQL permite realizar llamadas SQL en los datos. Es habitual combinar funciones definidas por el usuario y Spark SQL para aplicar una función definida por el usuario a todas las filas de DataFrame.

Puede llamar específicamente a `spark.Sql` para imitar las llamadas SQL estándar que se observan en otros tipos de aplicaciones. También puede llamar a métodos como <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> y <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> para combinar, filtrar y realizar cálculos en los datos de forma específica.

El objetivo de esta aplicación es obtener información detallada sobre los datos de los proyectos de GitHub. Agregue los siguientes fragmentos de código al programa para analizar los datos.

1. Al agregar el siguiente bloque de código se busca el número de veces que se ha bifurcado cada idioma. En primer lugar, los datos se agrupan por idioma. A continuación, se toma el número promedio de bifurcaciones de cada idioma.

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. Agregue el siguiente bloque de código para ordenar el promedio de bifurcaciones en orden descendente para ver los idiomas más bifurcados. Es decir, el mayor número de bifurcaciones aparecerá en primer lugar.

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. El siguiente bloque de código muestra cómo de recientemente se han actualizado los proyectos. Registre una nueva función definida por el usuario llamada *MyUDF* y compárela con una fecha, *s_referenceDate*, que se declaró al principio del tutorial. La fecha de cada proyecto se compara con la fecha de referencia. A continuación, Spark SQL se usa para llamar a la función definida por el usuario en cada fila de los datos para analizar cada proyecto del conjunto de datos.

   ```csharp
   spark.Udf().Register<string, bool>(
       "MyUDF",
       (date) => DateTime.TryParse(date, out DateTime convertedDate) &&
           (convertedDate > s_referenceDate);
   cleanedProjects.CreateOrReplaceTempView("dateView");

   DataFrame dateDf = spark.Sql(
       "SELECT *, MyUDF(dateView.updated_at) AS datebefore FROM dateView");
   dateDf.Show();
   ```

1. Llame a `spark.Stop()` para finalizar el objeto SparkSession.

## <a name="use-spark-submit-to-run-your-app"></a>Uso de spark-submit para ejecutar la aplicación

1. Use el comando siguiente para compilar la aplicación .NET:

   ```dotnetcli
   dotnet build
   ```

1. Ejecute la aplicación con `spark-submit`. Asegúrese de actualizar el siguiente comando con las rutas de acceso reales a su archivo .jar de Microsoft Spark.

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar dotnet /<path>/to/netcoreapp<version>/mySparkBatchApp.dll
   ```

## <a name="get-the-code"></a>Obtención del código

Puede ver la [solución completa](https://github.com/dotnet/spark/blob/main/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) en GitHub.

## <a name="next-steps"></a>Pasos siguientes

Avance al siguiente artículo para aprender a procesar datos de streaming con .NET para Apache Spark.
> [!div class="nextstepaction"]
> [Tutorial: Streaming estructurado con .NET para Apache Spark](streaming.md)

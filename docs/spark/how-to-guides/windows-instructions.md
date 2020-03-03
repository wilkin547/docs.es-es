---
title: Compilación de una aplicación de .NET para Apache Spark en Windows
description: Aprenda a compilar una aplicación de .NET para Apache Spark en Windows.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: 640459c8c80b6d798718b89d4965802cdacd6c63
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628662"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a>Aprenda a compilar una aplicación de .NET para Apache Spark en Windows

En este artículo se enseña cómo crear aplicaciones de .NET para Apache Spark en Windows.

## <a name="prerequisites"></a>Requisitos previos

Si ya cumple con todos los requisitos previos siguientes, vaya a los pasos de [compilación](#build).

  1. Descargue e instale el **[SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core/2.1)**. Al instalar el SDK, se agregará la cadena de herramientas `dotnet` a la variable de entorno PATH. Se admiten las versiones de .NET Core 2.1, 2.2 y 3.1.
  2. Instale **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (versión 16.3 o posterior). La versión Community es completamente gratis. Al configurar la instalación, incluya al menos estos componentes:
     * Desarrollo de escritorio de .NET
       * Todos los componentes necesarios
         * Herramientas de desarrollo de .NET Framework 4.6.1
     * Desarrollo multiplataforma de .NET Core
       * Todos los componentes necesarios
  3. Instale **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**. 
     - Seleccione la versión adecuada según su sistema operativo. Por ejemplo, *jdk-8u201-windows-x64.exe* si el equipo es Windows x64.
     - Use el instalador para realizar la instalación y compruebe que puede ejecutar `java` desde la línea de comandos.
  4. Instale **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.
     - Descargue [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).
     - Extraiga en un directorio local. Por ejemplo, *C:\bin\apache-maven-3.6.0\*.
     - Agregue Apache Maven a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml). Por ejemplo, *C:\bin\apache-maven-3.6.0\bin*.
     - Confirme que puede ejecutar `mvn` desde la línea de comandos.
  5. Instale **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.
     - Descargue [Apache Spark 2.3+](https://spark.apache.org/downloads.html) y extráigalo en una carpeta local (por ejemplo, *C:\bin\spark-2.3.2-bin-hadoop2.7\*), mediante [7-zip](https://www.7-zip.org/). (Las versiones compatibles de Spark son 2.3.*, 2.4.0, 2.4.1, 2.4.3 y 2.4.4)
     - Agregue una [variable de entorno nueva](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`. Por ejemplo, *C:\bin\spark-2.3.2-bin-hadoop2.7\*.

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\       
       ```

     - Agregue Apache Spark a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml). Por ejemplo, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.

       ```powershell       
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```
     
     - Confirme que puede ejecutar `spark-shell` desde la línea de comandos.        
        Salida de la consola de ejemplo:

        ```
        Welcome to
              ____              __
             / __/__  ___ _____/ /__
            _\ \/ _ \/ _ `/ __/  '_/
           /___/ .__/\_,_/_/ /_/\_\   version 2.3.2
              /_/

        Using Scala version 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
        Type in expressions to have them evaluated.
        Type :help for more information.

        scala> sc
        res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
        ```

        </details>

  6. Instale **[WinUtils](https://github.com/steveloughran/winutils)**.
     - Descargue el archivo binario `winutils.exe` del [repositorio de WinUtils](https://github.com/steveloughran/winutils). Debe seleccionar la versión de Hadoop con la que se ha compilado la distribución de Spark. Por ejemplo, use hadoop-2.7.1 para Spark 2.3.2.
     - Guarde el archivo binario `winutils.exe` en el directorio que elija. Por ejemplo, *C:\hadoop\bin*.
     - Establezca `HADOOP_HOME` para reflejar el directorio con winutils.exe (sin bin). Por ejemplo, con la línea de comandos:

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - Establezca la variable de entorno PATH para que incluya `%HADOOP_HOME%\bin`. Por ejemplo, con la línea de comandos:

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

Asegúrese de que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente. ¿Cree que hay una mejor manera de hacerlo? [Abra una incidencia](https://github.com/dotnet/spark/issues) y háganos llegar sus comentarios.

> [!NOTE]
> Es posible que sea necesaria una instancia nueva de la línea de comandos si se actualizaran las variables de entorno.

## <a name="build"></a>Compilar

En el resto de esta guía, deberá haber clonado el repositorio de .NET para Apache Spark en la máquina. Puede elegir cualquier ubicación para el repositorio clonado. Por ejemplo, *C:\github\dotnet-spark\*.

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a>Creación de la capa de extensiones de Scala de .NET para Apache Spark

Cuando se envía una aplicación de .NET, .NET para Apache Spark escribe en Scala la lógica necesaria que informa a Apache Spark cómo administrar las solicitudes (por ejemplo, solicitud para crear una sesión de Spark, solicitud para transferir datos desde el lado de .NET al lado de JVM, etc.). Esta lógica se puede encontrar en el [código fuente de Scala de .NET para Spark](https://github.com/dotnet/spark/tree/master/src/scala).

Independientemente de si usa .NET Framework o .NET Core, tendrá que crear la capa de extensiones de Scala de .NET para Apache Spark:

```powershell
cd src\scala
mvn clean package 
```

Debería ver los archivos JAR creados para las versiones compatibles de Spark:

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a>Compilación de las aplicaciones de ejemplo de .NET para Spark

En esta sección se explica cómo compilar las [aplicaciones de ejemplo](https://github.com/dotnet/spark/tree/master/examples) de .NET para Apache Spark. Estos pasos lo ayudarán a comprender el proceso general de compilación de cualquier aplicación de .NET para Spark.

#### <a name="using-visual-studio-for-net-framework"></a>Uso de Visual Studio para .NET Framework

  1. Abra `src\csharp\Microsoft.Spark.sln` en Visual Studio y compile el proyecto `Microsoft.Spark.CSharp.Examples` en la carpeta `examples` (a su vez, esto compilará también el proyecto de enlaces de .NET). Si quiere, puede escribir su propio código en el proyecto `Microsoft.Spark.Examples` (en este ejemplo, "input_file.json" es un archivo JSON con los datos con los que quiere crear la trama de datos):
  
      ```csharp
        // Instantiate a session
        var spark = SparkSession
            .Builder()
            .AppName("Hello Spark!")
            .GetOrCreate();

        // Create initial DataFrame
        DataFrame df = spark.Read().Json(input_file.json);

        // Print schema
        df.PrintSchema();

        // Apply a filter and show results
        df.Filter(df["age"] > 21).Show();
      ```

     Una vez que la compilación se realice correctamente, verá los archivos binarios adecuados en el directorio de salida.     
     Salida de la consola de ejemplo:
     
      ```powershell
            Directory: C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461


        Mode                LastWriteTime         Length Name
        ----                -------------         ------ ----
        -a----         3/6/2019  12:18 AM         125440 Apache.Arrow.dll
        -a----        3/16/2019  12:00 AM          13824 Microsoft.Spark.CSharp.Examples.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.CSharp.Examples.exe.config
        -a----        3/16/2019  12:00 AM           2720 Microsoft.Spark.CSharp.Examples.pdb
        -a----        3/16/2019  12:00 AM         143360 Microsoft.Spark.dll
        -a----        3/16/2019  12:00 AM          63388 Microsoft.Spark.pdb
        -a----        3/16/2019  12:00 AM          34304 Microsoft.Spark.Worker.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.Worker.exe.config
        -a----        3/16/2019  12:00 AM          11900 Microsoft.Spark.Worker.pdb
        -a----        3/16/2019  12:00 AM          23552 Microsoft.Spark.Worker.xml
        -a----        3/16/2019  12:00 AM         332363 Microsoft.Spark.xml
        ------------------------------------------- More framework files -------------------------------------
      ```     

#### <a name="using-net-core-cli-for-net-core"></a>Uso de la CLI de .NET Core para .NET Core

> [!NOTE]
> Actualmente, estamos trabajando en automatizar las compilaciones de .NET Core de .NET para Spark. Hasta entonces, agradecemos su paciencia al realizar algunos de los pasos manualmente.

  1. Compile el trabajo:

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
      
      Salida de la consola de ejemplo:

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish\
      ```    

  2. Compile los ejemplos:

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
   
      Salida de la consola de ejemplo:

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish\
      ```     

## <a name="run-the-net-for-spark-sample-applications"></a>Ejecución de las aplicaciones de ejemplo de .NET para Spark

Una vez que se compilan los ejemplos, su ejecución se realizará a través de `spark-submit` independientemente de si el destino es .NET Framework o .NET Core. Asegúrese de haber seguido la sección de [requisitos previos](#prerequisites) y de haber instalado Apache Spark.

  1. Establezca la variable de entorno `DOTNET_WORKER_DIR` o `PATH` para incluir la ruta de acceso en la que se ha generado el binario `Microsoft.Spark.Worker` (por ejemplo, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* para .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* para .NET Core):

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. Abra Powershell y vaya al directorio en el que se haya generado el archivo binario de la aplicación (por ejemplo, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* para .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* para .NET Core):

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. La ejecución de la aplicación sigue la estructura básica:

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     Estos son algunos ejemplos que se pueden ejecutar:

     - **[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (accesible por Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (proporcionado por jars)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd 
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```

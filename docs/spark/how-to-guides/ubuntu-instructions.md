---
title: Compilación de una aplicación de .NET para Apache Spark en Ubuntu
description: Aprenda a compilar una aplicación de .NET para Apache Spark en Ubuntu.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 77daad7298c41d21054db9174f30a8d1ed12648d
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687797"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a>Aprenda a compilar una aplicación de .NET para Apache Spark en Ubuntu.

En este artículo se enseña cómo crear aplicaciones de .NET para Apache Spark en Ubuntu.

## <a name="prerequisites"></a>Requisitos previos

Si ya cumple con todos los requisitos previos siguientes, vaya a los pasos de [compilación](#build).

1. Descargue e instale el **[SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)** ; al instalar el SDK, se agrega la cadena de herramientas `dotnet` a la ruta de acceso.  Se admiten las versiones de .NET Core 2.1, 2.2 y 3.1.

2. Instale **[OpenJDK 8](https://openjdk.java.net/install/)** .

   - Puede usar el comando siguiente:

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * Confirme que puede ejecutar `java` desde la línea de comandos.

      Salida de la versión de Java de ejemplo:

      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * Si ya tiene instaladas varias versiones de OpenJDK y quiere seleccionar OpenJDK 8, use este comando:

      ```bash
      sudo update-alternatives --config java
      ```

3. Instale **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)** .

   * Ejecute el siguiente comando:

      ```bash
      mkdir -p ~/bin/maven
      cd ~/bin/maven
      wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
      tar -xvzf apache-maven-3.6.0-bin.tar.gz
      ln -s apache-maven-3.6.0 current
      export M2_HOME=~/bin/maven/current
      export PATH=${M2_HOME}/bin:${PATH}
      source ~/.bashrc
      ```

       Tenga en cuenta que estas variables de entorno se perderán al cerrar el terminal. Si quiere que los cambios sean permanentes, agregue las líneas `export` al archivo `~/.bashrc`.

   * Confirme que puede ejecutar `mvn` desde la línea de comandos.

       Salida de la versión de mvn de ejemplo:

       ```output
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. Instale **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)** .
Descargue [Apache Spark 2.3+](https://spark.apache.org/downloads.html) y extráigalo en una carpeta local (por ejemplo, `~/bin/spark-3.0.1-bin-hadoop2.7`). Las versiones compatibles de Spark son 2.3.*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 y 3.0.1.

   ```bash
   tar -xvzf /path/to/spark-3.0.1-bin-hadoop2.7.tgz -C ~/bin/spark-3.0.1-bin-hadoop2.7
   ```

   * Agregue las [variables de entorno](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` (por ejemplo, `~/bin/spark-3.0.1-bin-hadoop2.7/`) y `PATH` (por ejemplo, `$SPARK_HOME/bin:$PATH`) necesarias.

      ```bash
      export SPARK_HOME=~/bin/spark-3.0.1-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```

      Tenga en cuenta que estas variables de entorno se perderán al cerrar el terminal. Si quiere que los cambios sean permanentes, agregue las líneas `export` al archivo `~/.bashrc`.

   * Confirme que puede ejecutar `spark-shell` desde la línea de comandos.

      Salida de la consola de ejemplo:

      ```
      Welcome to
            ____              __
           / __/__  ___ _____/ /__
          _\ \/ _ \/ _ `/ __/  '_/
         /___/ .__/\_,_/_/ /_/\_\   version 3.0.1
            /_/

      Using Scala version 2.12.10 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
      Type in expressions to have them evaluated.
      Type :help for more information.

      scala> sc
      res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
      ```

Asegúrese de que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente. ¿Cree que hay una mejor manera de hacerlo? [Abra una incidencia](https://github.com/dotnet/spark/issues) y háganos llegar sus comentarios.

## <a name="build"></a>Compilar

En el resto de esta guía, deberá haber clonado el repositorio de .NET para Apache Spark en la máquina, por ejemplo `~/dotnet.spark/`.

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a>Creación de la capa de extensiones de Scala de .NET para Spark

Cuando se envía una aplicación de .NET, .NET para Apache Spark tiene escrita en Scala la lógica necesaria que informa a Apache Spark cómo administrar las solicitudes (por ejemplo, solicitud para crear una sesión de Spark nueva, solicitud para transferir datos desde el lado de .NET al lado de JVM, etc.). Esta lógica se puede encontrar en el [código fuente de Scala de .NET para Apache Spark](https://github.com/dotnet/spark/tree/master/src/scala).

El paso siguiente es crear la capa de extensiones de Scala de .NET para Apache Spark:

```bash
cd src/scala
mvn clean package
```

Debería ver los archivos JAR creados para las versiones compatibles de Spark:

* `microsoft-spark-2-3\target\microsoft-spark-2-3_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-2-4\target\microsoft-spark-2-4_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-3-0\target\microsoft-spark-3-0_2.12-<spark-dotnet-version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a>Compilación de aplicaciones de .NET de ejemplo mediante la CLI de .NET Core

En esta sección se explica cómo compilar las [aplicaciones de ejemplo](https://github.com/dotnet/spark/tree/master/examples) de .NET para Apache Spark. Estos pasos lo ayudarán a comprender el proceso general de compilación de cualquier aplicación de .NET para Spark.

1. Compile el trabajo:

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   ```

   Salida de la consola de ejemplo:

   ```bash
   user@machine:/home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker$ dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 36.03 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker/Microsoft.Spark.Worker.csproj.
      Restore completed in 35.94 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.1/Microsoft.Spark.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/Microsoft.Spark.Worker.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/
   ```

2. Compile los ejemplos:

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   ```

   Salida de la consola de ejemplo:

   ```bash
   user@machine:/home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples$ dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 37.11 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Restore completed in 281.63 ms for /home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/Microsoft.Spark.CSharp.Examples.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.1/Microsoft.Spark.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/Microsoft.Spark.CSharp.Examples.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/
   ```  

## <a name="run-the-net-for-spark-sample-applications"></a>Ejecución de las aplicaciones de ejemplo de .NET para Spark

Una vez que compile los ejemplos, puede usar `spark-submit` para enviar sus aplicaciones de .NET Core. Asegúrese de haber seguido la sección de [requisitos previos](#prerequisites) y de haber instalado Apache Spark.

1. Establezca la variable de entorno `DOTNET_WORKER_DIR` o `PATH` para incluir la ruta de acceso donde se generó el archivo binario `Microsoft.Spark.Worker` (por ejemplo, `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`).

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish
   ```

2. Abra un terminal y vaya al directorio donde se generó el archivo binario de la aplicación (por ejemplo, `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`).

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish
   ```

3. La ejecución de la aplicación sigue la estructura básica:

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   Estos son algunos ejemplos que se pueden ejecutar:

   * **[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (accesible por Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (proporcionado por jars)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```

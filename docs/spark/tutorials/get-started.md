---
title: Introducción a .NET para Apache Spark
description: Descubra cómo ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577012"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Tutorial: Introducción a .NET para Apache Spark

En este tutorial aprenderá a ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.

En este tutorial, aprenderá a:

> [!div class="checklist"]
> * Preparar el entorno de Windows para .NET para Apache Spark
> * Descargar **Microsoft. Spark. Worker**
> * Compilar y ejecutar una aplicación .NET simple para Apache Spark

## <a name="prepare-your-environment"></a>Preparación del entorno

Antes de empezar, asegúrese de que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos. Si el entorno ya está preparado, puede ir directamente a la sección siguiente. Si no puede ejecutar ninguno o todos los comandos, siga los pasos que se indican a continuación.

1. Descargue e instale el [SDK de .net Core 2.1 x](https://dotnet.microsoft.com/download/dotnet-core/2.1). Al instalar el SDK, `dotnet` se agrega la cadena de herramientas a la ruta de acceso. Use el comando `dotnet --version` de PowerShell para comprobar la instalación.

2. Instale [visual studio 2017](https://www.visualstudio.com/downloads/) o [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) con las actualizaciones más recientes. Puede usar Community, Professional o Enterprise. La versión de la comunidad es gratuita.

   Elija las siguientes cargas de trabajo durante la instalación:
      * Desarrollo de escritorio de .NET
          * Todos los componentes necesarios
          * Herramientas de desarrollo de .NET Framework 4.6.1
      * Desarrollo multiplataforma de .NET Core
          * Todos los componentes necesarios

3. Instale [Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Seleccione la versión adecuada para su sistema operativo. Por ejemplo, seleccione **JDK-8u201-Windows-x64. exe** para un equipo Windows x64.
    * Use el comando `java -version` de PowerShell para comprobar la instalación.

4. Instale [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi).
    * Descargue [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).
    * Extraer en un directorio local. Por ejemplo, `c:\bin\apache-maven-3.6.0\`.
    * Agregue Apache Maven a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml). Si extrajo a `c:\bin\apache-maven-3.6.0\`, agregaría `c:\bin\apache-maven-3.6.0\bin` a la ruta de acceso.
    * Use el comando `mvn -version` de PowerShell para comprobar la instalación.

5. Instale [Apache Spark 2.3 +](https://spark.apache.org/downloads.html). Apache Spark 2.4 + no es compatible.
    * Descargue [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) y extráigalo en una carpeta local con una herramienta como [7-zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/). Por ejemplo, puede extraerlo a `c:\bin\spark-2.3.2-bin-hadoop2.7\`.
    * Agregue Apache Spark a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml). Si extrajo a `c:\bin\spark-2.3.2-bin-hadoop2.7\`, agregaría `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` a la ruta de acceso.
    * Agregue una [nueva variable](https://www.java.com/en/download/help/path.xml) de entorno `SPARK_HOME`denominada. Si extrajo a `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use `C:\bin\spark-2.3.2-bin-hadoop2.7\` para el **valor**de la variable.
    * Compruebe que puede ejecutar `spark-shell` desde la línea de comandos.

6. Configure [ausencia archivo winutils](https://github.com/steveloughran/winutils).
    * Descargue el archivo binario **ausencia archivo winutils. exe** del [repositorio ausencia archivo winutils](https://github.com/steveloughran/winutils). Seleccione la versión de Hadoop con la que se compiló la distribución de Spark. Por ejemplo, se usa **Hadoop-2.7.1** para **Spark 2.3.2**. La versión de Hadoop se anota al final del nombre de la carpeta de instalación de Spark.
    * Guarde el archivo binario de **ausencia archivo winutils. exe** en el directorio que prefiera. Por ejemplo, `c:\hadoop\bin`.
    * Se `HADOOP_HOME` establece para reflejar el directorio con **ausencia archivo winutils. exe** sin `bin`. Por ejemplo, `c:\hadoop`.
    * Establezca la variable de entorno PATH en `%HADOOP_HOME%\bin`include.

Haga doble comprobación de que puede `dotnet`ejecutar `java`, `mvn`, `spark-shell` , desde la línea de comandos antes de pasar a la sección siguiente.

## <a name="download-the-microsoftsparkworker-release"></a>Descargar la versión Microsoft. Spark. Worker

1. Descargue la versión [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) de la página .net para Apache Spark de las versiones de github en la máquina local. Por ejemplo, puede descargarla en la ruta de acceso `c:\bin\Microsoft.Spark.Worker\`,.

2. Cree una [nueva variable](https://www.java.com/en/download/help/path.xml) de entorno `DotnetWorkerPath` denominada y establézcala en el directorio donde descargó y extrajo **Microsoft. Spark. Worker**. Por ejemplo, `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Clonar el repositorio de .NET para Apache Spark GitHub

Use el siguiente comando de [GitBash](https://gitforwindows.org/) para clonar el Apache Spark de .net para el repositorio en la máquina.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Escritura de .NET para la aplicación Apache Spark

1. Abra **Visual Studio** y vaya a **archivo > crear nuevo proyecto > aplicación de consola (.net Core)** . Asigne a la aplicación el nombre **HelloSpark**.

2. Instale el [paquete NuGet Microsoft. Spark](https://www.nuget.org/profiles/spark). Para obtener más información sobre la instalación de paquetes NuGet, consulte [diferentes formas de instalar un paquete Nuget](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. En **Explorador de soluciones**, Abra **Program.CS** y escriba el código C# siguiente:

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Compile la solución.

## <a name="run-your-net-for-apache-spark-app"></a>Ejecución de .NET para la aplicación Apache Spark

1. Abra **PowerShell** y cambie el directorio a la carpeta donde se almacena la aplicación.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Cree un archivo denominado **People. JSON** con el siguiente contenido:

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. Use el siguiente comando de PowerShell para ejecutar la aplicación:

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

¡Enhorabuena! Ha creado y ejecutado correctamente .NET para Apache Spark aplicación.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial aprendió lo siguiente:
> [!div class="checklist"]
> * Preparar el entorno de Windows para .NET para Apache Spark
> * Descargar **Microsoft. Spark. Worker**
> * Compilar y ejecutar una aplicación .NET simple para Apache Spark

Consulte la página de recursos para obtener más información.
> [!div class="nextstepaction"]
> [.NET para recursos de Apache Spark](../resources/index.md)

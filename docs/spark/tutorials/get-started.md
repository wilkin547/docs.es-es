---
title: Introducción a .NET para Apache Spark
description: Sepa cómo ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577012"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Tutorial: Introducción a .NET para Apache Spark

En este tutorial aprenderá a ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows.

En este tutorial aprenderá a:

> [!div class="checklist"]
> * Preparar el entorno de Windows para .NET para Apache Spark
> * Descargar **Microsoft.Spark.Worker**
> * Compilar y ejecutar una aplicación de .NET para Apache Spark sencilla

## <a name="prepare-your-environment"></a>Preparación del entorno

Antes de empezar, asegúrese de que puede ejecutar `dotnet`, `java`, `mvn` y `spark-shell` desde la línea de comandos. Si el entorno ya está preparado, puede ir directamente a la siguiente sección. Si no puede ejecutar alguno o ninguno de los comandos, siga los pasos que se indican a continuación.

1. Descargue e instale el [SDK de .NET Core 2.1x](https://dotnet.microsoft.com/download/dotnet-core/2.1). Al instalar el SDK, se agrega la cadena de herramientas `dotnet` a la variable de entorno PATH. Use el comando de PowerShell `dotnet --version` para comprobar la instalación.

2. Instale [Visual Studio 2017](https://www.visualstudio.com/downloads/) o [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) con las actualizaciones más recientes. Puede usar las ediciones Community, Professional o Enterprise. La versión Community es gratuita.

   Elija las siguientes cargas de trabajo durante la instalación:
      * Desarrollo de escritorio de .NET
          * Todos los componentes necesarios
          * Herramientas de desarrollo de .NET Framework 4.6.1
      * Desarrollo multiplataforma de .NET Core
          * Todos los componentes necesarios

3. Instale [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Seleccione la versión adecuada según su sistema operativo. Así, por ejemplo, seleccione **jdk-8u201-windows-x64.exe** si el equipo es Windows x64.
    * Use el comando de PowerShell `java -version` para comprobar la instalación.

4. Instale [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).
    * Descargue [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).
    * Extraiga en un directorio local. Por ejemplo: `c:\bin\apache-maven-3.6.0\`.
    * Agregue Apache Maven a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml). Si extrajo en `c:\bin\apache-maven-3.6.0\`, habría que agregar `c:\bin\apache-maven-3.6.0\bin` a PATH.
    * Use el comando de PowerShell `mvn -version` para comprobar la instalación.

5. Instale [Apache Spark 2.3+](https://spark.apache.org/downloads.html). Apache Spark 2.4+ no se admite.
    * Descargue [Apache Spark 2.3+](https://spark.apache.org/downloads.html) y extráigalo en una carpeta local con una herramienta como [7-zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/). Por ejemplo, se puede extraer en `c:\bin\spark-2.3.2-bin-hadoop2.7\`.
    * Agregue Apache Spark a la [variable de entorno PATH](https://www.java.com/en/download/help/path.xml). Si extrajo en `c:\bin\spark-2.3.2-bin-hadoop2.7\`, habría que agregar `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` a PATH.
    * Agregue una [variable de entorno nueva](https://www.java.com/en/download/help/path.xml) llamada `SPARK_HOME`. Si extrajo en `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use `C:\bin\spark-2.3.2-bin-hadoop2.7\` en **Valor de la variable**.
    * Confirme que puede ejecutar `spark-shell` desde la línea de comandos.

6. Configure [WinUtils](https://github.com/steveloughran/winutils).
    * Descargue el archivo binario **winutils.exe** del [repositorio de WinUtils](https://github.com/steveloughran/winutils). Seleccione la versión de Hadoop con la que se compiló la distribución de Spark. Por ejemplo, para **Spark 2.3.2**, se usa **hadoop-2.7.1**. La versión de Hadoop aparece anotada al final del nombre de la carpeta de instalación de Spark.
    * Guarde el archivo binario **winutils.exe** en el directorio que prefiera. Por ejemplo: `c:\hadoop\bin`.
    * Establezca `HADOOP_HOME` para reflejar el directorio con **winutils.exe** sin `bin`. Por ejemplo: `c:\hadoop`.
    * Establezca la variable de entorno PATH para que incluya `%HADOOP_HOME%\bin`.

Confirme que puede ejecutar `dotnet`, `java`, `mvn`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente.

## <a name="download-the-microsoftsparkworker-release"></a>Descarga de la versión de Microsoft.Spark.Worker

1. Descargue en el equipo local la versión de [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) de la página de versiones de GitHub de .NET para Apache Spark. Por ejemplo, puede descargarlo en la ruta de acceso `c:\bin\Microsoft.Spark.Worker\`.

2. Cree una [variable de entorno](https://www.java.com/en/download/help/path.xml) llamada `DotnetWorkerPath` y establézcala en el directorio donde descargó y extrajo **Microsoft.Spark.Worker**. Por ejemplo: `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Clonado del repositorio de GitHub de .NET para Apache Spark

Use el siguiente comando de [GitBash](https://gitforwindows.org/) para clonar el repositorio de .NET para Apache Spark en el equipo.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Escritura de una aplicación de .NET para Apache Spark

1. Abra **Visual Studio** y vaya a **Archivo > Crear nuevo proyecto > Aplicación de consola (.NET Core)** . Asigne a la aplicación el nombre **HelloSpark**.

2. Instale el [paquete NuGet Microsoft.Spark](https://www.nuget.org/profiles/spark). Para más información sobre cómo instalar paquetes NuGet, vea [Formas de instalar un paquete NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. En el **Explorador de soluciones**, abra **Program.cs** y escriba el siguiente código de C#:

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Compile la solución.

## <a name="run-your-net-for-apache-spark-app"></a>Ejecución de la aplicación de .NET para Apache Spark

1. Abra **PowerShell** y cambie el directorio a la carpeta donde está almacenada la aplicación.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Cree un archivo denominado **people.json** con el siguiente contenido:

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

¡Enhorabuena! Ha creado y ejecutado correctamente una aplicación de .NET para Apache Spark.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> * Preparar el entorno de Windows para .NET para Apache Spark
> * Descargar **Microsoft.Spark.Worker**
> * Compilar y ejecutar una aplicación de .NET para Apache Spark sencilla

Eche un vistazo a la página de recursos para obtener más información.
> [!div class="nextstepaction"]
> [Recursos de .NET para Apache Spark](../resources/index.md)

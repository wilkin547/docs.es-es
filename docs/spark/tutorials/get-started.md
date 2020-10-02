---
title: Introducción a .NET para Apache Spark
description: Descubra cómo ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows, macOS y Ubuntu.
ms.date: 09/17/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 7afb35c9d02db1d1ee2bf04d565f79588b00695e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866050"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Tutorial: Introducción a .NET para Apache Spark

En este tutorial aprenderá a ejecutar una aplicación .NET para Apache Spark con .NET Core en Windows, macOS y Ubuntu.

En este tutorial aprenderá a:

> [!div class="checklist"]
>
> * Preparar el entorno de .NET para Apache Spark
> * Implementar la primer aplicación .NET para Apache Spark
> * Compilar y ejecutar una aplicación .NET para Apache Spark

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prepare-your-environment"></a>Preparación del entorno

Antes de comenzar a escribir la aplicación, debe configurar algunas dependencias de requisitos previos. Si puede ejecutar `dotnet`, `java`, `spark-shell`, desde el entorno de línea de comandos, el entorno ya está preparado y puede ir directamente a la sección siguiente. Si no puede ejecutar alguno o ninguno de los comandos, siga estos pasos.

### <a name="1-install-net"></a>1. Instalación de .NET

Para empezar a compilar aplicaciones .NET, debe descargar e instalar el SDK (kit de desarrollo de software) de .NET.

Descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.1). Al instalar el SDK, se agrega la cadena de herramientas `dotnet` a la variable de entorno PATH.

Una vez instalado el SDK de .NET Core, abra un símbolo del sistema o terminal nuevo y ejecute `dotnet`.

Si el comando se ejecuta e imprime información sobre cómo usar dotnet, puede pasar al paso siguiente. Si recibe un error `'dotnet' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema o terminal **nuevo** antes de ejecutar el comando.

### <a name="2-install-java"></a>2. Instalación de Java

Instale [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) para Windows y MacOS, o bien [OpenJDK 8](https://openjdk.java.net/install/) para Ubuntu.

Seleccione la versión adecuada según su sistema operativo. Por ejemplo, seleccione **jdk-8u201-windows-x64.exe** para una máquina Windows x64 (tal como se muestra debajo) o **jdk-8u231-macosx-x64.dmg** para macOS. Después, use el comando `java` para comprobar la instalación.

![Descarga de Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. Instalación de software de compresión

Apache Spark se descarga como un archivo .tgz comprimido. Use un programa de extracción, como[7-Zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/), para extraer el archivo.

### <a name="4-install-apache-spark"></a>4. Instalación de Apache Spark

[Descargue e instale](https://spark.apache.org/downloads.html) Apache Spark. Tendrá que seleccionar entre la versión 2.3.* o 2.4.0, 2.4.1, 2.4.3, o bien 2.4.4 (.NET para Apache Spark no es compatible con otras versiones de Apache Spark).

En los comandos que se usan en los pasos siguientes se supone que ha [descargado e instalado Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz). Si prefiere usar otra versión, reemplace **2.4.1** por el número de versión adecuado. Después, extraiga el archivo **.tar** y los archivos de Apache Spark.

Para extraer el archivo **.tar** anidado:

* Busque el archivo **spark-2.4.1-bin-hadoop2.7.tgz** que ha descargado.
* Haga clic con el botón derecho en el archivo y seleccione **7-Zip -> Extraer aquí**.
* Se creará **spark-2.4.1-bin-hadoop2.7.tar** junto con el archivo **.tgz** que ha descargado.

Para extraer los archivos de Apache Spark:

* Haga clic con el botón derecho en **spark-2.4.1-bin-hadoop2.7.tar** y seleccione **7-Zip -> Extraer archivos...**
* Escriba **C:\bin** en el campo **Extraer en**.
* Desactive la casilla situada debajo del campo **Extraer en**.
* Seleccione **Aceptar**.
* Los archivos de Apache Spark se extraen en C:\bin\spark-2.4.1-bin-hadoop2.7\.

![Instalación de Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

Ejecute los comandos siguientes para establecer las variables de entorno que se usan para buscar Apache Spark. En Windows, asegúrese de ejecutar el símbolo del sistema en modo de administrador.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[Mac o Linux:](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

Una vez que se haya instalado todo y establecido las variables de entorno, abra un símbolo del sistema o terminal **nuevo** y ejecute el comando siguiente:

```text
spark-submit --version
```

Si el comando se ejecuta e imprime la información de versión, puede pasar al paso siguiente.

Si recibe un error `'spark-submit' is not recognized as an internal or external command`, asegúrese de que ha abierto un símbolo del sistema **nuevo**.

### <a name="5-install-net-for-apache-spark"></a>5. Instalación de .NET para Apache Spark

Descargue la versión [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) de la página de .NET para Apache Spark en GitHub. Por ejemplo, si se encuentra en una máquina Windows y planea usar .NET Core, [descargue la versión Windows x64 netcoreapp3.1](https://github.com/dotnet/spark/releases).

Para extraer Microsoft.Spark.Worker:

* Busque el archivo **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** que ha descargado.
* Haga clic con el botón derecho y seleccione **7-Zip -> Extraer archivos...**
* Escriba **C:\bin** en el campo **Extraer en**.
* Desactive la casilla situada debajo del campo **Extraer en**.
* Seleccione **Aceptar**.

![Instalación de .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a>6. Instalación de WinUtils (solo Windows)

.NET para Apache Spark requiere que se instale WinUtils junto a Apache Spark. [Descargue winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Después, copie WinUtils en **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Si usa otra versión de Hadoop (anotada al final del nombre de la carpeta de instalación de Spark) [seleccione la versión de WinUtils](https://github.com/steveloughran/winutils) que sea compatible con la versión de Hadoop.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Establecimiento de DOTNET_WORKER_DIR y comprobación de las dependencias

Ejecute uno de los comandos siguientes para establecer la variable de entorno `DOTNET_WORKER_DIR`, que las aplicaciones .NET usan con el fin de buscar .NET para Apache Spark. Asegúrese de reemplazar `<PATH-DOTNET_WORKER_DIR>` por el directorio donde descargó y extrajo el `Microsoft.Spark.Worker`. En Windows, asegúrese de ejecutar el símbolo del sistema en modo de administrador.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[Mac o Linux:](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

Por último, confirme que puede ejecutar `dotnet`, `java`, `spark-shell` desde la línea de comandos antes de pasar a la sección siguiente.

## <a name="write-a-net-for-apache-spark-app"></a>Escritura de una aplicación de .NET para Apache Spark

### <a name="1-create-a-console-app"></a>1. Crear una aplicación de consola

En el símbolo del sistema o terminal, ejecute los comandos siguientes para crear una aplicación de consola nueva:

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

El comando `dotnet` crea una aplicación `new` de tipo `console` de forma automática. El parámetro `-o` crea un directorio denominado *mySparkApp* donde se almacena la aplicación y lo rellena con los archivos necesarios. El comando `cd MySparkApp` cambia el directorio al directorio de la aplicación que acaba de crear.

### <a name="2-install-nuget-package"></a>2. Instalación del paquete NuGet

Para usar .NET para Apache Spark en una aplicación, instale el paquete Microsoft.Spark. En el símbolo del sistema o terminal, ejecute el comando siguiente:

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> En este tutorial se usa la versión más reciente del paquete NuGet de `Microsoft.Spark`, a menos que se especifique lo contrario.

### <a name="3-write-your-app"></a>3. Escritura de la aplicación

Abra *Program.cs* en Visual Studio Code o cualquier editor de texto, y reemplace todo el código por lo siguiente:

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

El objeto [SparkSession](xref:Microsoft.Spark.Sql.SparkSession) es el punto de entrada de las aplicaciones Apache Spark, que administra el contexto y la información de la aplicación. Mediante el método [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A), los datos de texto del archivo especificado por `filePath` se leen en un [DataFrame](xref:Microsoft.Spark.Sql.DataFrame). Un DataFrame es una manera de organizar los datos en un conjunto de columnas con nombre. A continuación, se aplica una serie de transformaciones para dividir las frases en el archivo, agrupar cada una de las palabras, contarlas y ordenarlas en orden descendente. El resultado de estas operaciones se almacena en otro DataFrame. Tenga en cuenta que, en este momento, no se ha realizado ninguna operación porque .NET para Apache Spark evalúa los datos de forma diferida. No es hasta que se llama al método [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) para mostrar el contenido del DataFrame transformado `words` en la consola que se ejecutan las operaciones definidas en las líneas anteriores. Cuando ya no necesite la sesión de Spark, use el método [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) para detener la sesión.

### <a name="4-create-data-file"></a>4. Creación del archivo de datos

La aplicación procesa un archivo que contiene líneas de texto. Cree un archivo llamado *input.txt* en el directorio *MySparkApp*, con el texto siguiente:

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

Guarde los cambios y cierre el archivo.

## <a name="run-your-net-for-apache-spark-app"></a>Ejecución de la aplicación de .NET para Apache Spark

Ejecute el comando siguiente para compilar la aplicación:

```dotnetcli
dotnet build
```

Desplácese al directorio de salida de la compilación y use el comando `spark-submit` para enviar la aplicación para que se ejecute en Apache Spark. Asegúrese de reemplazar `<version>` por la versión del trabajo de .NET y `<path-of-input.txt>` por la ruta de acceso del archivo *input.txt* donde está almacenado.

### <a name="windows"></a>[Windows](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-2.4.x-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[Mac o Linux:](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-2.4.x-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> Este comando asume que se ha descargado Apache Spark y se ha agregado a la variable de entorno PATH para poder usar `spark-submit`. De lo contrario, tendría que usar la ruta de acceso completa (por ejemplo, *C:\bin\apache-spark\bin\spark-submit* o *~/spark/bin/spark-submit*).

Cuando la aplicación se ejecuta, los datos de recuento de palabras del archivo *input.txt* se escriben en la consola.

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

¡Enhorabuena! Ha creado y ejecutado correctamente una aplicación de .NET para Apache Spark.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> * Preparar el entorno de .NET para Apache Spark
> * Implementar la primer aplicación .NET para Apache Spark
> * Compilar y ejecutar una aplicación .NET para Apache Spark

Para ver un vídeo en el que se explican los pasos anteriores, consulte la [serie de vídeos .NET para Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).

Eche un vistazo a la página de recursos para obtener más información.
> [!div class="nextstepaction"]
> [Recursos de .NET para Apache Spark](../resources/index.md)

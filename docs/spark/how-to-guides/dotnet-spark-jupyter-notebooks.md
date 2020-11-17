---
title: Uso de Jupyter Notebooks
titleSuffix: .NET for Apache Spark
description: Uso de .NET para Apache Spark en entornos interactivos como Jupyter Notebook, Jupyter Lab o Visual Studio Code (VS Code)
ms.author: luquinta
author: luisquintanilla
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc, how-to
ms.openlocfilehash: eb285465fcacc3e7d4ee60765c30497dcefbc737
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441068"
---
# <a name="use-net-for-apache-spark-in-jupyter-notebooks"></a>Uso de .NET para Apache Spark en cuadernos de Jupyter Notebook

En este artículo, aprenderá a ejecutar trabajos de .NET para Apache Spark de forma interactiva en Jupyter Notebook y Visual Studio Code (VS Code) con .NET Interactive.

## <a name="about-jupyter"></a>Acerca de Jupyter

[Jupyter](https://jupyter.org/) es un entorno informático multiplataforma de código abierto que permite a los usuarios crear prototipos y desarrollar aplicaciones de forma interactiva. Puede interactuar con Jupyter a través de una amplia variedad de interfaces como Jupyter Notebook, Jupyter Lab y VS Code.

En el contexto de .NET, [.NET Interactive](https://github.com/dotnet/interactive), una herramienta global de .NET Core, proporciona un kernel para escribir código de .NET (C# o F#) en entornos informáticos interactivos como Jupyter Notebook.

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 3.1](../../core/install/index.yml)
- [Spark de Apache](https://spark.apache.org/downloads.html)
- [Trabajo de .NET para Apache Spark](https://github.com/dotnet/spark/releases)

Vea el [tutorial de introducción](../tutorials/get-started.md) para obtener más información sobre cómo configurar el entorno de .NET para Apache Spark.

## <a name="prepare-environment"></a>Preparación del entorno

Para trabajar con cuadernos de Jupyter Notebook, necesitará dos cosas.

1. Instalar la [herramienta global de .NET .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md).
1. Descargar el paquete NuGet `Microsoft.Spark`.
    1. Vaya hasta la página del paquete NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/).

        > [!IMPORTANT]
        > De forma predeterminada, se descarga la versión más reciente del paquete. **Asegúrese de que la versión que descarga es la misma que la del trabajo de .NET para Apache Spark.**

    1. En el panel **Info** (Información), seleccione **Download package** (Descargar paquete) para descargar la versión más reciente del paquete. El nombre del paquete es similar a *microsoft.spark.[VERSIÓN_DEL_PAQUETE].nupkg*.
    1. Descomprima el paquete descargado. El directorio descomprimido debe contener un subdirectorio con el nombre *jars*. Anote la ruta de acceso, ya que se usará más adelante.

## <a name="start-net-for-apache-spark"></a>Inicio de .NET para Apache Spark

Ejecute el comando siguiente para iniciar .NET para Apache Spark en modo de depuración. Este comando `spark-submit` inicia un proceso y espera conexiones de un objeto [SparkSession](xref:Microsoft.Spark.Sql.SparkSession). Asegúrese de proporcionar la ruta de acceso al archivo `microsoft-spark-<version>.jar` de la versión correspondiente de .NET para Apache Spark que use.

**Ubuntu**

```bash
spark-submit \
    --class org.apache.spark.deploy.dotnet.DotnetRunner \
    --master local \
    <path-to-microsoft-spark-jar> \
    debug
```

**Windows**

```cmd
spark-submit ^
    --class org.apache.spark.deploy.dotnet.DotnetRunner ^
    --master local ^
    <path-to-microsoft-spark-jar> ^
    debug
```

## <a name="create-a-notebook"></a>Creación de un cuaderno

Puede usar diferentes interfaces para interactuar con Jupyter. Para una interfaz basada en el explorador, use cuadernos de Jupyter Notebook o Jupyter Lab. Para una experiencia de editor local, use VS Code.

### <a name="jupyter-notebooks--jupyter-lab"></a>Cuadernos de Jupyter Notebook y Jupyter Lab

1. En otro símbolo del sistema, inicie Jupyter Notebook o Jupyter Lab con uno de los comandos siguientes:

    **Jupyter Notebook**

    ```bash
    jupyter notebook
    ```

    **Jupyter Lab**

    ```bash
    jupyter lab
    ```

    Estos comandos inician una ventana del explorador con la interfaz de Jupyter Notebook o Jupyter Lab.

1. En el explorador, cree un cuaderno.

    **Jupyter Notebook**

    Seleccione **Nuevo > .NET (C#)** o **Nuevo > .NET (F#)**

    **Jupyter Lab**

    En la ventana Launcher, seleccione **.NET (C#)** o **.NET (F#)**

### <a name="visual-studio-code-preview"></a>Visual Studio Code (versión preliminar)

> [!IMPORTANT]
> Para usar cuadernos de Jupyter Notebook en VS Code, debe instalar lo siguiente:
>
>- [VS Code Insiders](https://code.visualstudio.com/insiders/)
>- [La extensión .NET Interactive Notebooks](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-interactive-vscode)

1. Abra VS Code.
1. Abra la paleta de comandos **Ver > Paleta de comandos**.

    Cuando aparezca la paleta de comandos, escriba el comando siguiente para crear un cuaderno de .NET Interactive:

    ```text
    >.NET Interactive: Create new blank notebook
    ```

    Como alternativa, si quiere abrir un cuaderno de .NET Interactive existente con la extensión *.ipynb*, use el comando siguiente:

    ```text
    >.NET Interactive: Open notebook
    ```

## <a name="initialize-a-spark-session"></a>Inicialización de una sesión de Spark

1. Cuando se abra el cuaderno, instale el paquete NuGet `Microsoft.Spark`. Asegúrese de que la versión que instala es la misma que la del trabajo de .NET.

    ```text
    #r "nuget:Microsoft.Spark, 0.12.1"
    ```

1. Agregue la siguiente instrucción using al cuaderno.

    ```csharp
    using Microsoft.Spark.Sql;
    ```

1. Inicialice el objeto [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).

    ```csharp
    var sparkSession =
    SparkSession
        .Builder()
        .AppName("dotnet-interactive-spark")
        .GetOrCreate();
    ```

El cuaderno debe ser similar al de la imagen siguiente. En este ejemplo se usa VS Code, pero Jupyter Notebook y Jupyter Lab deberían tener un aspecto similar.

> [!div class="mx-imgBorder"]
![.NET para Apache Spark, Jupyter Notebook y VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)

## <a name="next-steps"></a>Pasos siguientes

- [Introducción a .NET para Apache Spark](../tutorials/get-started.md)
- [Predicción de opiniones con .NET para Apache Spark y ML.NET](../tutorials/ml-sentiment-analysis.md)
- Para obtener más información sobre .NET Interactive, vea la [documentación de .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/README.md).

---
title: 'Introducción a .NET Core con la CLI: CLI de .NET Core'
description: Un tutorial paso a paso que muestra cómo empezar a trabajar con .NET Core en Windows, Linux o macOS con la interfaz de la línea de comandos (CLI) de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: 6c394ad2721bcdd91fb750fe93c03f16ca9f799f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714074"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos

En este artículo se muestra cómo empezar a desarrollar aplicaciones multiplataforma en su máquina con las herramientas de la CLI de .NET Core.

Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).

## <a name="prerequisites"></a>Requisitos previos

- [SDK 3.1 de NET Core](https://dotnet.microsoft.com/download) o versiones posteriores.
- Un editor de texto o un editor de código de su elección.

## <a name="hello-console-app"></a>Hola, aplicación de consola

Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) del repositorio dotnet/samples de GitHub. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Abra un símbolo del sistema y cree una carpeta denominada *Hello*. Vaya a la carpeta que ha creado y escriba lo siguiente:

```dotnetcli
dotnet new console
dotnet run
```

Veamos un tutorial rápido:

01. `dotnet new console`

    [dotnet new](../tools/dotnet-new.md) crea un archivo de proyecto *Hello.csproj* actualizado con las dependencias necesarias para compilar una aplicación de consola. Además, también crea *Program.cs*, un archivo básico que contiene el punto de entrada para la aplicación.
    
    *Hello.csproj*:
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.
    
    - El elemento `<OutputType>` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.
    - El elemento `<TargetFramework>` especifica el destino de la implementación de .NET. En un escenario avanzado, con una sola operación puede especificar varios marcos de destino y compilar en todos ellos. En este tutorial, nos centraremos en compilar únicamente para .NET Core 3.1.
    
    *Program.cs*:
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo". El espacio de nombres `System` incluye la clase `Console`.
    
    Después, definimos un espacio de nombres denominado `Hello`. Puede cambiar esto por cualquier cosa que desee. Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas llamada `args`. Esta matriz contiene la lista de argumentos que se han pasado cuando se ejecuta el programa. Esta matriz no se usa tal cual y el programa escribe simplemente el texto "¡Hola mundo!". en la consola. Después, realizaremos cambios en el código que usará este argumento.
    
    `dotnet new` llama a [dotnet restore](../tools/dotnet-restore.md) de forma implícita. `dotnet restore` llama a [NuGet](https://www.nuget.org/) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias. NuGet analiza el archivo *Hello.csproj*, descarga las dependencias descritas en el archivo (o las toma de la memoria caché del equipo) y escribe el archivo *obj/project.assets.json*, que es necesario para compilar y ejecutar el ejemplo.

02. `dotnet run`

    [dotnet run](../tools/dotnet-run.md) llama a [dotnet build](../tools/dotnet-build.md) para garantizar que se han creado los destinos de compilación y, luego, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.
    
    ```console
    dotnet run

    Hello World!
    ```
    
    También puede ejecutar `dotnet build` para compilar el código sin ejecutar las aplicaciones de consola de compilación. El resultado es una aplicación compilada, como un archivo DLL, basada en el nombre del proyecto. En este caso, el archivo creado se llama *Hello.dll*. Esta aplicación se puede ejecutar con `dotnet bin\Debug\netcoreapp3.1\Hello.dll` en Windows (use `/` con sistemas que no son Windows).
    
    ```console
    dotnet bin\Debug\netcoreapp3.1\Hello.dll

    Hello World!
    ```
    
    Cuando se compila la aplicación, se crea un archivo ejecutable específico del sistema operativo junto con `Hello.dll`. En Windows, sería `Hello.exe`; en Linux o macOS, sería `hello`. Con el ejemplo anterior, el archivo se designa con `Hello.exe` o `Hello`. Puede ejecutar ese archivo ejecutable directamente.

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a>Modificación del programa

Cambiemos un poco el programa. Los números Fibonacci son divertidos, así que vamos a agregarlos y a usar además el argumento para saludar a la persona que ejecuta la aplicación.

01. Reemplace el contenido de su archivo *Program.cs* por el código siguiente:

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. Ejecute [dotnet build](../tools/dotnet-build.md) para compilar los cambios.

03. Para ejecutar el programa, pase un parámetro a la aplicación. Cuando use el comando `dotnet` para ejecutar una aplicación, agregue `--` al final. Todo lo que quede a la derecha de `--` se pasará como un parámetro a la aplicación. En el ejemplo siguiente, el valor `John` se pasa a la aplicación.

    ```console
    $ dotnet run -- John
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

Y listo. Puede modificar *Program.cs* como prefiera.

## <a name="working-with-multiple-files"></a>Trabajar con varios archivos

Los archivos únicos son adecuados para programas sencillos de uso único, pero, si va a crear una aplicación más compleja, probablemente llegue a tener varios archivos de código en el proyecto. Se compilará sobre el ejemplo de Fibonacci anterior mediante el almacenamiento en caché de algunos valores de Fibonacci y la adición de varias características recursivas.

01. Agregue un archivo nuevo dentro del directorio *Hello* denominado *FibonacciGenerator.cs* con el código siguiente:

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. Cambie el método `Main` en su archivo *Program.cs* para crear una instancia de la nueva clase y llamar a su método como se muestra en el ejemplo siguiente:

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. Ejecute [dotnet build](../tools/dotnet-build.md) para compilar los cambios.

04. Ejecute su aplicación mediante la ejecución de [dotnet run](../tools/dotnet-run.md). A continuación se muestra el resultado del programa:

    ```console
    $ dotnet run
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a>Publicar la aplicación

Cuando esté listo para distribuir la aplicación, use el comando [dotnet publish](../tools/dotnet-publish.md)_para generar la carpeta_publish _en \\bin\\debug\\netcoreapp3.1\\publish_`/` (para sistemas que no son Windows). Puede distribuir el contenido de la carpeta _publish_ en otras plataformas siempre y cuando ya haya instalado el entorno de ejecución de dotnet.

```console
dotnet publish
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

Puede que la salida anterior no sea igual por la carpeta y el sistema operativo actuales, pero el resultado será parecido.

Puede ejecutar la aplicación publicada con el comando [dotnet](../tools/dotnet.md):

```console
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll

Hello World!
```

Como se ha mencionado al comienzo de este artículo, se ha creado un archivo ejecutable específico del sistema operativo junto con `Hello.dll`. En Windows, sería `Hello.exe`; en Linux o macOS, sería `hello`. Con el ejemplo anterior, el archivo se designa con `Hello.exe` o `Hello`. Puede ejecutar este archivo ejecutable publicado directamente.

```console
.\bin\Debug\netcoreapp3.1\Hello.exe

Hello World!
```

## <a name="conclusion"></a>Conclusión

Y listo. Ahora, puede empezar a usar los conceptos básicos que ha aprendido aquí para crear sus propios programas.

## <a name="see-also"></a>Vea también

- [Organización y prueba de proyectos con las herramientas de la CLI de .NET Core](testing-with-cli.md)
- [Publicación de aplicaciones .NET Core con la CLI](../deploying/deploy-with-cli.md)
- [Más información acerca de la implementación](../deploying/index.md)

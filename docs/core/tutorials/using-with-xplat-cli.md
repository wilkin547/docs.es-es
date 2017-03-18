---
title: "Introducción a .NET Core con la CLI | Microsoft Docs"
description: "Un tutorial paso a paso que muestra cómo empezar a trabajar con .NET Core en Windows, Linux o macOS con la interfaz de la línea de comandos (CLI) de .NET Core."
keywords: .NET Core, CLI
author: cartermp
ms.author: mairaw
ms.date: 02/08/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 41632e63-d5c6-4427-a09e-51dc1116d45f
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 240061d2515c14ba7ab733f4cc9e7e38fb2a5c7c
ms.lasthandoff: 03/07/2017

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Introducción a .NET Core en Windows/Linux/macOS con la línea de comandos

Este tema le mostrará cómo empezar a desarrollar aplicaciones multiplataforma en su equipo con las herramientas de la CLI de .NET Core.

Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).

## <a name="prerequisites"></a>Requisitos previos

- [SDK 1.0.0 de .NET Core](https://www.microsoft.com/net/download/core).
- Un editor de texto o un editor de código de su elección.

## <a name="hello-console-app"></a>Hola, aplicación de consola

En primer lugar, navegue o cree una nueva carpeta con el nombre que desee. *Hello* es el nombre elegido para el código de ejemplo, que se puede encontrar [aquí](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild).

Abra un símbolo del sistema y escriba lo siguiente:

```
$ dotnet new console
$ dotnet restore
$ dotnet run
```

Veamos un tutorial rápido:

1. `$ dotnet new console`

[`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.  Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.
   
`Hello.csproj`:

[!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]   

   El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.

   * La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.
   * La etiqueta `TargetFramework` especifica el entorno de ejecución de .NET al que nos dirigimos. En un escenario avanzado, puede especificar varios marcos de destino y compilar en todos ellos en una sola operación. En este tutorial, nos centraremos solo en .NET Core 1.0.

   `Program.cs`:

[!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]   

   El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo". El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.

   Después, definimos un espacio de nombres denominado `Hello`. Puede cambiar esto por cualquier cosa que desee. Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento. Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado. Tal y como está, esta matriz no se usa: todo lo que hace el programa es escribir "¡Hola a todos!" en la consola. Después, realizaremos cambios en el código que usará este argumento.

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md) llama a [NuGet](http://nuget.org) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias. NuGet analiza el archivo *Hello.csproj*, descarga las dependencias descritas en el archivo (o las toma de la memoria caché del equipo) y escribe el archivo *obj/project.assets.json*.  El archivo *project.assets.json* es necesario para realizar la compilación y ejecución.
   
   El archivo *project.assets.json* es un conjunto completo y persistente del gráfico de dependencias de NuGet y cualquier otra información que describa una aplicación.  Este archivo se lee por otras herramientas, como [`dotnet build`](../tools/dotnet-build.md) y [`dotnet run`](../tools/dotnet-run.md), que les permite procesar el código fuente con un conjunto correcto de las dependencias de NuGet y resoluciones de enlace.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para asegurarse de que los destinos de la compilación se han creado y, después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.
   
    ```
    $ dotnet run
    Hello World!
    ```

    También puede ejecutar [`dotnet build`](../tools/dotnet-build.md) para compilar el código sin ejecutar las aplicaciones de consola de compilación. El resultado es una aplicación compilada como un archivo DLL que se puede ejecutar con `dotnet bin\Debug\netcoreapp1.0\Hello.dll` en Windows (use `/` para otros sistemas que no sean de Windows). También puede especificar argumentos específicos para la aplicación como verá posteriormente en el tema.

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll
    Hello World!
    ```

    Como escenario avanzado, es posible compilar la aplicación como un conjunto autocontenido de archivos específicos de la plataforma que se puede implementar y ejecutar en una máquina que no tiene necesariamente instalado .NET Core. Consulte [Implementación de aplicaciones .NET Core](../deploying/index.md) para más información.

### <a name="augmenting-the-program"></a>Aumento del programa

Cambiemos un poco el programa. Los números Fibonacci son divertidos, así que vamos a agregarlos además de usar el argumento para saludar a la persona que ejecuta la aplicación.

1. Reemplace el contenido de su archivo *Program.cs* por el código siguiente:

[!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]   

2. Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.

3. Ejecute el programa pasando un parámetro a la aplicación:

```
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

Y listo.  Puede aumentar `Program.cs` como desee.

## <a name="working-with-multiple-files"></a>Trabajar con varios archivos

Los archivos únicos están bien para los programas sencillos de uso único, pero si está compilando una aplicación más compleja, probablemente va a tener varios archivos de origen en su proyecto. Vamos a crear el ejemplo de Fibonacci anterior almacenando en caché algunos valores de Fibonacci y agregando algunas características recursivas. 

1. Agregue un archivo nuevo dentro del directorio *Hello* denominado *FibonacciGenerator.cs* con el código siguiente:

[!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]   

2. Cambie el método `Main` en su archivo *Program.cs* para crear una instancia de la nueva clase y llamar a su método como se muestra en el ejemplo siguiente:

[!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.

4. Ejecute su aplicación con la ejecución de [`dotnet run`](../tools/dotnet-run.md). A continuación se muestra el resultado del programa:

```
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

Y listo. Ahora, puede empezar a usar los conceptos básicos que ha aprendido aquí para crear sus propios programas.

Tenga en cuenta que los comandos y los pasos que se muestran en este tutorial para ejecutar la aplicación se usan solo durante el desarrollo. Una vez que esté listo para implementar la aplicación, querrá echar un vistazo a las diferentes [estrategias de implementación](../deploying/index.md) para aplicaciones de .NET Core y al comando [`dotnet publish`](../tools/dotnet-publish.md).

## <a name="see-also"></a>Vea también

[Organización y prueba de proyectos con las herramientas de la CLI de .NET Core](testing-with-cli.md)

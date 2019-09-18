---
title: Introducción a .NET Core con la CLI
description: Un tutorial paso a paso que muestra cómo empezar a trabajar con .NET Core en Windows, Linux o macOS con la interfaz de la línea de comandos (CLI) de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 08/07/2019
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: c42a34bc13ff9fb5d8eb5a85b461360915e2c68f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849339"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos

Este tema le mostrará cómo empezar a desarrollar aplicaciones multiplataforma en su equipo con las herramientas de la CLI de .NET Core.

Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, vea la [información general del SDK de .NET Core](../tools/index.md).

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core](https://dotnet.microsoft.com/download), versión 2.1 o posterior.
- Un editor de texto o un editor de código de su elección.

## <a name="hello-console-app"></a>Hola, aplicación de consola

Puede [ver o descargar el código de ejemplo](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) del repositorio dotnet/samples de GitHub. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Abra un símbolo del sistema y cree una carpeta denominada *Hello*. Vaya a la carpeta que ha creado y escriba lo siguiente:

```console
dotnet new console
dotnet run
```

Veamos un tutorial rápido:

1. `dotnet new console`

   [`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.  Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.

   `Hello.csproj`:

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.

   - La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.
   - La etiqueta `TargetFramework` especifica la implementación .NET a la que nos dirigimos. En un escenario avanzado, con una sola operación puede especificar varios marcos de destino y compilar en todos ellos. En este tutorial, nos centraremos en compilar únicamente para .NET Core 2.1.

   `Program.cs`:

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]

   El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo". El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.

   Después, definimos un espacio de nombres denominado `Hello`. Puede cambiar esto por cualquier cosa que desee. Se define una clase denominada `Program` dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento. Esta matriz contiene la lista de argumentos que se ha pasado cuando se llama al programa compilado. Tal y como está, esta matriz no se usa: todo lo que hace el programa es escribir "¡Hola a todos!" en la consola. Después, realizaremos cambios en el código que usará este argumento.

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   `dotnet new` llama a [`dotnet restore`](../tools/dotnet-restore.md) de forma implícita. `dotnet restore` llama a [NuGet](https://www.nuget.org/) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias. NuGet analiza el archivo *Hello.csproj*, descarga las dependencias descritas en el archivo (o las toma de la memoria caché del equipo) y escribe el archivo *obj/project.assets.json*, que es necesario para compilar y ejecutar el ejemplo.

   > [!IMPORTANT]
   > Si usa una versión .NET Core 1.x del SDK, tendrá que llamar a `dotnet restore` usted mismo después de llamar a `dotnet new`.

2. `dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para asegurarse de que los destinos de la compilación se han creado y, después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.

    ```console
    $ dotnet run
    Hello World!
    ```

    También puede ejecutar [`dotnet build`](../tools/dotnet-build.md) para compilar el código sin ejecutar las aplicaciones de consola de compilación. El resultado es una aplicación compilada como un archivo DLL que se puede ejecutar con `dotnet bin\Debug\netcoreapp2.1\Hello.dll` en Windows (use `/` para otros sistemas que no sean de Windows). También puede especificar argumentos para la aplicación como verá posteriormente en el tema.

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    Como escenario avanzado, es posible compilar la aplicación como un conjunto autocontenido de archivos específicos de la plataforma que se puede implementar y ejecutar en una máquina que no tiene necesariamente instalado .NET Core. Consulte [Implementación de aplicaciones .NET Core](../deploying/index.md) para más información.

### <a name="augmenting-the-program"></a>Aumento del programa

Cambiemos un poco el programa. Los números Fibonacci son divertidos, así que vamos a agregarlos además de usar el argumento para saludar a la persona que ejecuta la aplicación.

1. Reemplace el contenido de su archivo *Program.cs* por el código siguiente:

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.

3. Ejecute el programa pasando un parámetro a la aplicación:

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

Y listo.  Puede aumentar `Program.cs` como desee.

## <a name="working-with-multiple-files"></a>Trabajar con varios archivos

Los archivos únicos son adecuados para programas sencillos de uso único, pero, si va a crear una aplicación más compleja, probablemente tendrá varios archivos de origen en el proyecto.
Se compilará sobre el ejemplo de Fibonacci anterior mediante el almacenamiento en caché de algunos valores de Fibonacci y la adición de varias características recursivas.

1. Agregue un archivo nuevo dentro del directorio *Hello* denominado *FibonacciGenerator.cs* con el código siguiente:

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. Cambie el método `Main` en su archivo *Program.cs* para crear una instancia de la nueva clase y llamar a su método como se muestra en el ejemplo siguiente:

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. Ejecute [`dotnet build`](../tools/dotnet-build.md) para compilar los cambios.

4. Ejecute su aplicación con la ejecución de [`dotnet run`](../tools/dotnet-run.md). A continuación se muestra el resultado del programa:

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

## <a name="publish-your-app"></a>Publicación de la aplicación

Una vez que esté listo para distribuir la aplicación, use el comando [`dotnet publish`](../tools/dotnet-publish.md) para generar la carpeta _publish_ en _bin\\debug\\netcoreapp2.1\\publish\\_ (utilice `/` para sistemas que no son de Windows). Puede distribuir el contenido de la carpeta _publish_ en otras plataformas siempre y cuando ya haya instalado el entorno de ejecución de dotnet.

Puede ejecutar la aplicación publicada con el comando [dotnet](../tools/dotnet.md):

```console
$ dotnet bin\Debug\netcoreapp2.1\publish\Hello.dll
Hello World!
```

## <a name="conclusion"></a>Conclusión

Y listo. Ahora, puede empezar a usar los conceptos básicos que ha aprendido aquí para crear sus propios programas.

## <a name="see-also"></a>Vea también

- [Organización y prueba de proyectos con las herramientas de la CLI de .NET Core](testing-with-cli.md)
- [Publicación de aplicaciones .NET Core con la CLI](../deploying/deploy-with-cli.md)
- [Más información acerca de la implementación](../deploying/index.md)

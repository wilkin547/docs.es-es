---
title: 'Tutorial: Creación de una herramienta de .NET'
description: Obtenga información sobre cómo crear una herramienta de .NET. Una herramienta es una aplicación de consola que se instala mediante la CLI de .NET.
ms.topic: tutorial
ms.date: 12/14/2020
ms.openlocfilehash: dc5cf014336848ff1a3035647a386419653a083b
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633902"
---
# <a name="tutorial-create-a-net-tool-using-the-net-cli"></a>Tutorial: Creación de una herramienta de .NET mediante la CLI de .NET

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

En este tutorial se explica cómo crear y empaquetar una herramienta de .NET. La CLI de .NET permite crear una aplicación de consola como una herramienta, que otros usuarios pueden instalar y ejecutar. Las herramientas de .NET son paquetes NuGet que se instalan desde la CLI de .NET. Para obtener más información sobre las herramientas, vea [Información general sobre las herramientas de .NET](global-tools.md).

La herramienta que se va a crear es una aplicación de consola que toma un mensaje como entrada y muestra el mensaje junto con líneas de texto que crean la imagen de un robot.

Este es el primero en una serie de tres tutoriales. En este tutorial, creará y empaquetará una herramienta. En los dos tutoriales siguientes, [usará la herramienta como una herramienta global](global-tools-how-to-use.md) y [usará la herramienta como una herramientas local](local-tools-how-to-use.md). Los procedimientos para crear una herramienta son los mismos tanto si se usan como una herramienta global o como una herramienta local.

## <a name="prerequisites"></a>Requisitos previos

- [SDK 5.0.100 de .NET](https://dotnet.microsoft.com/download) o una versión posterior.

  En este tutorial se usa el SDK de .NET 5.0, pero las herramientas globales están disponibles a partir del SDK de .NET Core 2.1. Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.

- Un editor de texto o un editor de código de su elección.

## <a name="create-a-project"></a>Crear un proyecto

1. Abra un símbolo del sistema y cree una carpeta denominada *repositorio*.

1. Desplácese hasta la carpeta *repository* y escriba el comando siguiente:

   ```dotnetcli
   dotnet new console -n microsoft.botsay -f net5.0
   ```

   El comando crea una carpeta denominada *microsoft.botsay* en la carpeta *repository*.

   > [!NOTE]
   > En este tutorial se crea una herramienta que tiene como destino .NET 5.0. Para que el destino sea otra plataforma, cambie la opción `-f|--framework`. Para que el destino sean varias plataformas, cambie el elemento `TargetFramework` a un elemento `TargetFrameworks` en el archivo de proyecto, como se muestra en el ejemplo siguiente:
   >
   > ```xml
   > <Project Sdk="Microsoft.NET.Sdk">
   >   <PropertyGroup>
   >     <OutputType>Exe</OutputType>
   >     <TargetFrameworks>netcoreapp3.1;net5.0</TargetFrameworks>
   >   </PropertyGroup>
   > </Project>
   > ```

1. Navegue hasta la carpeta *microsoft.botsay*.

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a>Agregar el código

1. Abra el archivo `Program.cs` con el editor de código.

1. Agregue la siguiente directiva `using` al principio del archivo:

   ```csharp
   using System.Reflection;
   ```

1. Reemplace el método `Main` con el siguiente código para procesar los argumentos de la línea de comandos para la aplicación.

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   Si no se pasó ningún argumento, se muestra un mensaje de ayuda breve. De lo contrario, todos los argumentos se concatenan en una sola cadena y se imprimen llamando al método `ShowBot` que se crea en el paso siguiente.

1. Agregue un nuevo método denominado `ShowBot` que toma un parámetro de cadena. El método imprime el mensaje y una imagen de un robot usando líneas de texto.

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. Guarde los cambios.

## <a name="test-the-application"></a>Probar la aplicación

Ejecute el proyecto y observe la salida. Pruebe estas variaciones en la línea de comandos para ver resultados diferentes:

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

Todos los argumentos después del delimitador `--` se pasan a la aplicación.

## <a name="package-the-tool"></a>Empaquetado de la herramienta

Antes de que pueda empaquetar y distribuir la aplicación como una herramienta, debe modificar el archivo de proyecto.

1. Abra el archivo *microsoft.botsay.csproj* y agregue tres nuevos nodos XML al final del nodo `<PropertyGroup>`:

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   `<ToolCommandName>` es un elemento opcional que especifica el comando que invocará a la herramienta una vez instalada. Si no se proporciona este elemento, el nombre de comando para la herramienta es el nombre del archivo de proyecto sin la extensión *.csproj*.

   `<PackageOutputPath>` es un elemento opcional que determina dónde se generará el paquete NuGet. El paquete NuGet es el que la CLI de .NET utiliza para instalar la herramienta.

   El archivo del proyecto debe ser similar al siguiente ejemplo:

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>net5.0</TargetFramework>

       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>

     </PropertyGroup>

   </Project>
   ```

1. Cree un paquete NuGet ejecutando el comando [dotnet pack](dotnet-pack.md):

   ```dotnetcli
   dotnet pack
   ```

   El archivo *microsoft.botsay.1.0.0.nupkg* se crea en la carpeta identificada por el valor `<PackageOutputPath>` del archivo *microsoft.botsay.csproj*, que en este ejemplo es la carpeta *./nupkg*.

   Si quiere lanzar una herramienta públicamente, puede cargarla en `https://www.nuget.org`. Una vez que la herramienta está disponible en NuGet, los desarrolladores pueden instalar la herramienta mediante el comando [dotnet tool install](dotnet-tool-install.md). En este tutorial, se instalará el paquete directamente desde la carpeta local *nupkg*, por lo que no es necesario cargar el paquete en NuGet.

## <a name="troubleshoot"></a>Solucionar problemas

Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una aplicación de consola y la ha empaquetado como una herramienta. Para aprender a usar la herramienta como una herramienta global, avance al siguiente tutorial.

> [!div class="nextstepaction"]
> [Instalación y uso de una herramienta global](global-tools-how-to-use.md)

Si lo prefiere, puede omitir el tutorial de herramientas globales y pasar directamente al tutorial de herramientas locales.

> [!div class="nextstepaction"]
> [Instalación y uso de una herramienta local](local-tools-how-to-use.md)

---
title: 'Tutorial: Creación de una herramienta de .NET Core'
description: Descubra cómo crear una herramienta de .NET Core. La herramienta es una aplicación de consola que se instala mediante la CLI de .NET Core.
ms.date: 02/12/2020
ms.openlocfilehash: 88cc3be7b149834ace0c5f3ba8ac8c039199908f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156730"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a>Tutorial: Creación de una herramienta de .NET Core mediante la CLI de .NET Core

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

En este tutorial se explica cómo crear y empaquetar una herramienta en .NET Core. La CLI de .NET Core permite crear una aplicación de consola como una herramienta, que otros usuarios pueden instalar y ejecutar. Las herramientas de .NET Core son paquetes de NuGet que se instalan desde la CLI de .NET Core. Para obtener más información sobre las herramientas, vea [Información general sobre las herramientas de .NET Core](global-tools.md).

La herramienta que se va a crear es una aplicación de consola que toma un mensaje como entrada y muestra el mensaje junto con líneas de texto que crean la imagen de un robot.

Este es el primero en una serie de tres tutoriales. En este tutorial, creará y empaquetará una herramienta. En los dos tutoriales siguientes, [usará la herramienta como una herramienta global](global-tools-how-to-use.md) y [usará la herramienta como una herramientas local](local-tools-how-to-use.md).

## <a name="prerequisites"></a>Requisitos previos

- [SDK 3.1 de NET Core](https://dotnet.microsoft.com/download) o una versión posterior.

  Este tutorial y el siguiente [tutorial para las herramientas globales](global-tools-how-to-use.md) se aplican al SDK de .NET Core 2.1 y versiones posteriores, porque las herramientas globales están disponibles a partir de esa versión. Pero en este tutorial se da por supuesto que tiene instalada la versión 3.1 o posterior para que tenga la opción de continuar con el [tutorial de herramientas locales](local-tools-how-to-use.md). Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0. Los procedimientos para crear una herramienta son los mismos tanto si se usan como una herramienta global o como una herramienta local.
  
- Un editor de texto o un editor de código de su elección.

## <a name="create-a-project"></a>Crear un proyecto

1. Abra un símbolo del sistema y cree una carpeta denominada *repositorio*.

1. Desplácese hasta la carpeta *repository* y escriba el comando siguiente:

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   El comando crea una carpeta denominada *microsoft.botsay* en la carpeta *repository*.

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

   `<PackageOutputPath>` es un elemento opcional que determina dónde se generará el paquete NuGet. El paquete NuGet es el que la CLI de .NET Core utiliza para instalar la herramienta.

   El archivo del proyecto debe ser similar al siguiente ejemplo:

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>netcoreapp3.1</TargetFramework>
  
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

Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una aplicación de consola y la ha empaquetado como una herramienta. Para aprender a usar la herramienta como una herramienta global, avance al siguiente tutorial.

> [!div class="nextstepaction"]
> [Instalación y uso de una herramienta global](global-tools-how-to-use.md)

Si lo prefiere, puede omitir el tutorial de herramientas globales y pasar directamente al tutorial de herramientas locales.

> [!div class="nextstepaction"]
> [Instalación y uso de una herramienta local](local-tools-how-to-use.md)

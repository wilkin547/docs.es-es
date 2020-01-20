---
title: Creación de una herramienta global en .NET Core
description: Se describe cómo crear una herramienta global. La herramienta global es una aplicación de consola que se instala mediante la CLI de .NET Core.
author: Thraka
ms.author: adegeo
ms.date: 08/22/2018
ms.openlocfilehash: 1daecf7234f02a5fe0dcf25cf7edbb0af327b8c1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343519"
---
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a>Creación de una herramienta global de .NET Core mediante la CLI de .NET Core

En este artículo se explica cómo crear y empaquetar una herramienta global en .NET Core. La CLI de .NET Core permite crear una aplicación de consola como una herramienta global, que otros usuarios pueden instalar y ejecutar fácilmente. Las herramientas globales de .NET Core son paquetes de NuGet que se instalan desde la CLI de .NET Core. Para más información sobre las herramientas globales, vea [Información general sobre las herramientas globales de .NET Core](global-tools.md).

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a>Crear un proyecto

En este artículo se usa la CLI de .NET Core para crear y administrar un proyecto.

Nuestra herramienta de ejemplo será una aplicación de consola que genera un bot de ASCII e imprime un mensaje. En primer lugar, cree una aplicación de consola de .NET Core.

```dotnetcli
dotnet new console -o botsay
```

Navegue hasta el directorio `botsay` creado por el comando anterior.

## <a name="add-the-code"></a>Agregar el código

Abra el archivo `Program.cs` con su editor de texto favorito, como `vim` o [Visual Studio Code](https://code.visualstudio.com/).

Agregue la siguiente directiva `using` a la parte superior del archivo, ya que esto ayuda a reducir el código para mostrar la información de versión de la aplicación.

```csharp
using System.Reflection;
```

A continuación, desplácese hacia abajo hasta el método `Main`. Reemplace el método con el siguiente código para procesar los argumentos de la línea de comandos para la aplicación. Si no se pasa ningún argumento, se muestra un mensaje de Ayuda breve. En caso contrario, todos los argumentos se transforman en una cadena y se imprimen con el bot.

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

### <a name="create-the-bot"></a>Crear el bot

A continuación, agregue un nuevo método denominado `ShowBot` que toma un parámetro de cadena. Este método imprime el mensaje y el bot de ASCII. El código de bot de ASCII se ha tomado del ejemplo de [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs).

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

### <a name="test-the-tool"></a>Probar la herramienta

Ejecute el proyecto y observe la salida. Pruebe estas variaciones en la línea de comandos para ver resultados diferentes:

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

Todos los argumentos después del delimitador `--` se pasan a la aplicación.

## <a name="set-up-the-global-tool"></a>Configuración de la herramienta global

Antes de que pueda empaquetar y distribuir la aplicación como una herramienta global, debe modificar el archivo de proyecto. Abra el archivo `botsay.csproj` y agregue tres nuevos nodos XML al nodo `<Project><PropertyGroup>`:

- `<PackAsTool>`\
[OBLIGATORIO] Indica que la aplicación se empaquetará para la instalación como una herramienta global.

- `<ToolCommandName>`\
[OPCIONAL] Un nombre alternativo para la herramienta; en caso contrario, el nombre del comando de la herramienta se asignará después del archivo de proyecto. Puede tener varias herramientas en un paquete; elegir un nombre único y descriptivo ayuda a diferenciar de otras herramientas en el mismo paquete.

- `<PackageOutputPath>`\
[OPCIONAL] Dónde se generará el paquete NuGet. El paquete NuGet es el que las herramientas globales de la CLI de .NET Core utilizan para instalar la herramienta.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>

    <PackAsTool>true</PackAsTool>
    <ToolCommandName>botsay</ToolCommandName>
    <PackageOutputPath>./nupkg</PackageOutputPath>

  </PropertyGroup>

</Project>
```

Aunque `<PackageOutputPath>` es opcional, úselo en este ejemplo. Asegúrese de que lo establece: `<PackageOutputPath>./nupkg</PackageOutputPath>`.

A continuación, cree un paquete NuGet para la aplicación.

```dotnetcli
dotnet pack
```

El archivo `botsay.1.0.0.nupkg` se crea en la carpeta identificada por el valor XML `<PackageOutputPath>` desde el archivo `botsay.csproj`, que en este ejemplo es la carpeta `./nupkg`. Esto facilita la instalación y las pruebas. Si quiere lanzar una herramienta públicamente, cárguela en <https://www.nuget.org>. Una vez que la herramienta está disponible en NuGet, los desarrolladores pueden realizar una instalación para todos los usuarios de dicha herramienta mediante la opción `--global` del comando [dotnet tool install](dotnet-tool-install.md).

Ahora que tiene un paquete, instale la herramienta desde ese paquete:

```dotnetcli
dotnet tool install --global --add-source ./nupkg botsay
```

El parámetro `--add-source` indica a la CLI de .NET Core que use temporalmente la carpeta `./nupkg` (nuestra carpeta `<PackageOutputPath>`) como una fuente de origen adicional para los paquetes NuGet. Para más información sobre la instalación de las herramientas globales, vea [Información general sobre las herramientas globales de .NET Core](global-tools.md).

Si la instalación es correcta, se muestra un mensaje similar al siguiente con el comando que se usa para llamar a la herramienta y la versión instalada:

```output
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

Ahora podrá escribir `botsay` y obtener una respuesta de la herramienta.

> [!NOTE]
> Si la instalación fue correcta, pero no se puede usar el comando `botsay`, es posible que deba abrir un terminal nuevo para actualizar la ruta de acceso.

## <a name="remove-the-tool"></a>Quitar la herramienta

Cuando haya terminado de experimentar con la herramienta, puede quitarla con el comando siguiente:

```dotnetcli
dotnet tool uninstall -g botsay
```

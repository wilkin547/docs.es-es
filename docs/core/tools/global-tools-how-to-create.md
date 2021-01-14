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
# <a name="tutorial-create-a-net-tool-using-the-net-cli"></a><span data-ttu-id="af127-104">Tutorial: Creación de una herramienta de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="af127-104">Tutorial: Create a .NET tool using the .NET CLI</span></span>

<span data-ttu-id="af127-105">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="af127-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="af127-106">En este tutorial se explica cómo crear y empaquetar una herramienta de .NET.</span><span class="sxs-lookup"><span data-stu-id="af127-106">This tutorial teaches you how to create and package a .NET tool.</span></span> <span data-ttu-id="af127-107">La CLI de .NET permite crear una aplicación de consola como una herramienta, que otros usuarios pueden instalar y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="af127-107">The .NET CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="af127-108">Las herramientas de .NET son paquetes NuGet que se instalan desde la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="af127-108">.NET tools are NuGet packages that are installed from the .NET CLI.</span></span> <span data-ttu-id="af127-109">Para obtener más información sobre las herramientas, vea [Información general sobre las herramientas de .NET](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af127-109">For more information about tools, see [.NET tools overview](global-tools.md).</span></span>

<span data-ttu-id="af127-110">La herramienta que se va a crear es una aplicación de consola que toma un mensaje como entrada y muestra el mensaje junto con líneas de texto que crean la imagen de un robot.</span><span class="sxs-lookup"><span data-stu-id="af127-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="af127-111">Este es el primero en una serie de tres tutoriales.</span><span class="sxs-lookup"><span data-stu-id="af127-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="af127-112">En este tutorial, creará y empaquetará una herramienta.</span><span class="sxs-lookup"><span data-stu-id="af127-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="af127-113">En los dos tutoriales siguientes, [usará la herramienta como una herramienta global](global-tools-how-to-use.md) y [usará la herramienta como una herramientas local](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="af127-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span> <span data-ttu-id="af127-114">Los procedimientos para crear una herramienta son los mismos tanto si se usan como una herramienta global o como una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="af127-114">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af127-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="af127-115">Prerequisites</span></span>

- <span data-ttu-id="af127-116">[SDK 5.0.100 de .NET](https://dotnet.microsoft.com/download) o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="af127-116">[.NET SDK 5.0.100](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="af127-117">En este tutorial se usa el SDK de .NET 5.0, pero las herramientas globales están disponibles a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="af127-117">This tutorial uses .NET SDK 5.0, but global tools are available starting in .NET Core SDK 2.1.</span></span> <span data-ttu-id="af127-118">Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="af127-118">Local tools are available starting in .NET Core SDK 3.0.</span></span>

- <span data-ttu-id="af127-119">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="af127-119">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="af127-120">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="af127-120">Create a project</span></span>

1. <span data-ttu-id="af127-121">Abra un símbolo del sistema y cree una carpeta denominada *repositorio*.</span><span class="sxs-lookup"><span data-stu-id="af127-121">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="af127-122">Desplácese hasta la carpeta *repository* y escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="af127-122">Navigate to the *repository* folder and enter the following command:</span></span>

   ```dotnetcli
   dotnet new console -n microsoft.botsay -f net5.0
   ```

   <span data-ttu-id="af127-123">El comando crea una carpeta denominada *microsoft.botsay* en la carpeta *repository*.</span><span class="sxs-lookup"><span data-stu-id="af127-123">The command creates a new folder named *microsoft.botsay* under the *repository* folder.</span></span>

   > [!NOTE]
   > <span data-ttu-id="af127-124">En este tutorial se crea una herramienta que tiene como destino .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="af127-124">For this tutorial you create a tool that targets .NET 5.0.</span></span> <span data-ttu-id="af127-125">Para que el destino sea otra plataforma, cambie la opción `-f|--framework`.</span><span class="sxs-lookup"><span data-stu-id="af127-125">To target a different framework, change the `-f|--framework` option.</span></span> <span data-ttu-id="af127-126">Para que el destino sean varias plataformas, cambie el elemento `TargetFramework` a un elemento `TargetFrameworks` en el archivo de proyecto, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="af127-126">To target multiple frameworks, change the `TargetFramework` element to a `TargetFrameworks` element in the project file, as shown in the following example:</span></span>
   >
   > ```xml
   > <Project Sdk="Microsoft.NET.Sdk">
   >   <PropertyGroup>
   >     <OutputType>Exe</OutputType>
   >     <TargetFrameworks>netcoreapp3.1;net5.0</TargetFrameworks>
   >   </PropertyGroup>
   > </Project>
   > ```

1. <span data-ttu-id="af127-127">Navegue hasta la carpeta *microsoft.botsay*.</span><span class="sxs-lookup"><span data-stu-id="af127-127">Navigate to the *microsoft.botsay* folder.</span></span>

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a><span data-ttu-id="af127-128">Agregar el código</span><span class="sxs-lookup"><span data-stu-id="af127-128">Add the code</span></span>

1. <span data-ttu-id="af127-129">Abra el archivo `Program.cs` con el editor de código.</span><span class="sxs-lookup"><span data-stu-id="af127-129">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="af127-130">Agregue la siguiente directiva `using` al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="af127-130">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="af127-131">Reemplace el método `Main` con el siguiente código para procesar los argumentos de la línea de comandos para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af127-131">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

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

   <span data-ttu-id="af127-132">Si no se pasó ningún argumento, se muestra un mensaje de ayuda breve.</span><span class="sxs-lookup"><span data-stu-id="af127-132">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="af127-133">De lo contrario, todos los argumentos se concatenan en una sola cadena y se imprimen llamando al método `ShowBot` que se crea en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="af127-133">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="af127-134">Agregue un nuevo método denominado `ShowBot` que toma un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="af127-134">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="af127-135">El método imprime el mensaje y una imagen de un robot usando líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="af127-135">The method prints out the message and an image of a robot using lines of text.</span></span>

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

1. <span data-ttu-id="af127-136">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="af127-136">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="af127-137">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="af127-137">Test the application</span></span>

<span data-ttu-id="af127-138">Ejecute el proyecto y observe la salida.</span><span class="sxs-lookup"><span data-stu-id="af127-138">Run the project and see the output.</span></span> <span data-ttu-id="af127-139">Pruebe estas variaciones en la línea de comandos para ver resultados diferentes:</span><span class="sxs-lookup"><span data-stu-id="af127-139">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="af127-140">Todos los argumentos después del delimitador `--` se pasan a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af127-140">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="af127-141">Empaquetado de la herramienta</span><span class="sxs-lookup"><span data-stu-id="af127-141">Package the tool</span></span>

<span data-ttu-id="af127-142">Antes de que pueda empaquetar y distribuir la aplicación como una herramienta, debe modificar el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="af127-142">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span>

1. <span data-ttu-id="af127-143">Abra el archivo *microsoft.botsay.csproj* y agregue tres nuevos nodos XML al final del nodo `<PropertyGroup>`:</span><span class="sxs-lookup"><span data-stu-id="af127-143">Open the *microsoft.botsay.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="af127-144">`<ToolCommandName>` es un elemento opcional que especifica el comando que invocará a la herramienta una vez instalada.</span><span class="sxs-lookup"><span data-stu-id="af127-144">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="af127-145">Si no se proporciona este elemento, el nombre de comando para la herramienta es el nombre del archivo de proyecto sin la extensión *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="af127-145">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="af127-146">`<PackageOutputPath>` es un elemento opcional que determina dónde se generará el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="af127-146">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="af127-147">El paquete NuGet es el que la CLI de .NET utiliza para instalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="af127-147">The NuGet package is what the .NET CLI uses to install your tool.</span></span>

   <span data-ttu-id="af127-148">El archivo del proyecto debe ser similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="af127-148">The project file now looks like the following example:</span></span>

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

1. <span data-ttu-id="af127-149">Cree un paquete NuGet ejecutando el comando [dotnet pack](dotnet-pack.md):</span><span class="sxs-lookup"><span data-stu-id="af127-149">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="af127-150">El archivo *microsoft.botsay.1.0.0.nupkg* se crea en la carpeta identificada por el valor `<PackageOutputPath>` del archivo *microsoft.botsay.csproj*, que en este ejemplo es la carpeta *./nupkg*.</span><span class="sxs-lookup"><span data-stu-id="af127-150">The *microsoft.botsay.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *microsoft.botsay.csproj* file, which in this example is the *./nupkg* folder.</span></span>

   <span data-ttu-id="af127-151">Si quiere lanzar una herramienta públicamente, puede cargarla en `https://www.nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="af127-151">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="af127-152">Una vez que la herramienta está disponible en NuGet, los desarrolladores pueden instalar la herramienta mediante el comando [dotnet tool install](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="af127-152">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="af127-153">En este tutorial, se instalará el paquete directamente desde la carpeta local *nupkg*, por lo que no es necesario cargar el paquete en NuGet.</span><span class="sxs-lookup"><span data-stu-id="af127-153">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="af127-154">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="af127-154">Troubleshoot</span></span>

<span data-ttu-id="af127-155">Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="af127-155">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="af127-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="af127-156">Next steps</span></span>

<span data-ttu-id="af127-157">En este tutorial, ha creado una aplicación de consola y la ha empaquetado como una herramienta.</span><span class="sxs-lookup"><span data-stu-id="af127-157">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="af127-158">Para aprender a usar la herramienta como una herramienta global, avance al siguiente tutorial.</span><span class="sxs-lookup"><span data-stu-id="af127-158">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="af127-159">Instalación y uso de una herramienta global</span><span class="sxs-lookup"><span data-stu-id="af127-159">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="af127-160">Si lo prefiere, puede omitir el tutorial de herramientas globales y pasar directamente al tutorial de herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="af127-160">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="af127-161">Instalación y uso de una herramienta local</span><span class="sxs-lookup"><span data-stu-id="af127-161">Install and use a local tool</span></span>](local-tools-how-to-use.md)

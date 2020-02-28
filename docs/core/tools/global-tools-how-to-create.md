---
title: 'Tutorial: Creación de una herramienta de .NET Core'
description: Descubra cómo crear una herramienta de .NET Core. La herramienta es una aplicación de consola que se instala mediante la CLI de .NET Core.
ms.date: 02/12/2020
ms.openlocfilehash: 558bf9e37efc8de68a61f1384fababe342ab7d66
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543409"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a><span data-ttu-id="8ee2a-104">Tutorial: Creación de una herramienta de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="8ee2a-104">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>

<span data-ttu-id="8ee2a-105">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="8ee2a-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="8ee2a-106">En este tutorial se explica cómo crear y empaquetar una herramienta en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-106">This tutorial teaches you how to create and package a .NET Core tool.</span></span> <span data-ttu-id="8ee2a-107">La CLI de .NET Core permite crear una aplicación de consola como una herramienta, que otros usuarios pueden instalar y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-107">The .NET Core CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="8ee2a-108">Las herramientas de .NET Core son paquetes de NuGet que se instalan desde la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-108">.NET Core tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="8ee2a-109">Para obtener más información sobre las herramientas, vea [Información general sobre las herramientas de .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8ee2a-109">For more information about tools, see [.NET Core tools overview](global-tools.md).</span></span>

<span data-ttu-id="8ee2a-110">La herramienta que se va a crear es una aplicación de consola que toma un mensaje como entrada y muestra el mensaje junto con líneas de texto que crean la imagen de un robot.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="8ee2a-111">Este es el primero en una serie de tres tutoriales.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="8ee2a-112">En este tutorial, creará y empaquetará una herramienta.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="8ee2a-113">En los dos tutoriales siguientes, [usará la herramienta como una herramienta global](global-tools-how-to-use.md) y [usará la herramienta como una herramientas local](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="8ee2a-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ee2a-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8ee2a-114">Prerequisites</span></span>

- <span data-ttu-id="8ee2a-115">[SDK 3.1 de NET Core](https://dotnet.microsoft.com/download) o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-115">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="8ee2a-116">Este tutorial y el siguiente [tutorial para las herramientas globales](global-tools-how-to-use.md) se aplican al SDK de .NET Core 2.1 y versiones posteriores, porque las herramientas globales están disponibles a partir de esa versión.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-116">This tutorial and the following [tutorial for global tools](global-tools-how-to-use.md) apply to .NET Core SDK 2.1 and later versions because global tools are available starting in that version.</span></span> <span data-ttu-id="8ee2a-117">Pero en este tutorial se da por supuesto que tiene instalada la versión 3.1 o posterior para que tenga la opción de continuar con el [tutorial de herramientas locales](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="8ee2a-117">But this tutorial assumes you have installed 3.1 or later so that you have the option of continuing on to the [local tools tutorial](local-tools-how-to-use.md).</span></span> <span data-ttu-id="8ee2a-118">Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-118">Local tools are available starting in .NET Core SDK 3.0.</span></span> <span data-ttu-id="8ee2a-119">Los procedimientos para crear una herramienta son los mismos tanto si se usan como una herramienta global o como una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-119">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>
  
- <span data-ttu-id="8ee2a-120">Un editor de texto o un editor de código de su elección.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-120">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="8ee2a-121">Crear un proyecto</span><span class="sxs-lookup"><span data-stu-id="8ee2a-121">Create a project</span></span>

1. <span data-ttu-id="8ee2a-122">Abra un símbolo del sistema y cree una carpeta denominada *repositorio*.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-122">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="8ee2a-123">Vaya a la carpeta *repositorio* y escriba el siguiente comando, reemplazando `<name>` por un valor único para que el nombre del proyecto sea único.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-123">Navigate to the *repository* folder and enter the following command, replacing `<name>` with a unique value to make the project name unique.</span></span> 

   ```dotnetcli
   dotnet new console -n botsay-<name>
   ```

   <span data-ttu-id="8ee2a-124">Por ejemplo, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8ee2a-124">For example, you could run the following command:</span></span>

   ```dotnetcli
   dotnet new console -n botsay-nancydavolio
   ```

   <span data-ttu-id="8ee2a-125">El comando crea una nueva carpeta denominada *botsay-\<name>* en la carpeta *repositorio*.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-125">The command creates a new folder named *botsay-\<name>* under the *repository* folder.</span></span>

1. <span data-ttu-id="8ee2a-126">Vaya a la carpeta *botsay-\<name>* .</span><span class="sxs-lookup"><span data-stu-id="8ee2a-126">Navigate to the *botsay-\<name>* folder.</span></span>

   ```console
   cd botsay-<name>
   ```

## <a name="add-the-code"></a><span data-ttu-id="8ee2a-127">Agregar el código</span><span class="sxs-lookup"><span data-stu-id="8ee2a-127">Add the code</span></span>

1. <span data-ttu-id="8ee2a-128">Abra el archivo `Program.cs` con el editor de código.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-128">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="8ee2a-129">Agregue la siguiente directiva `using` al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="8ee2a-129">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="8ee2a-130">Reemplace el método `Main` con el siguiente código para procesar los argumentos de la línea de comandos para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-130">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

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

   <span data-ttu-id="8ee2a-131">Si no se pasó ningún argumento, se muestra un mensaje de ayuda breve.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-131">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="8ee2a-132">De lo contrario, todos los argumentos se concatenan en una sola cadena y se imprimen llamando al método `ShowBot` que se crea en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-132">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="8ee2a-133">Agregue un nuevo método denominado `ShowBot` que toma un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-133">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="8ee2a-134">El método imprime el mensaje y una imagen de un robot usando líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-134">The method prints out the message and an image of a robot using lines of text.</span></span>

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

1. <span data-ttu-id="8ee2a-135">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-135">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="8ee2a-136">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="8ee2a-136">Test the application</span></span>

<span data-ttu-id="8ee2a-137">Ejecute el proyecto y observe la salida.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-137">Run the project and see the output.</span></span> <span data-ttu-id="8ee2a-138">Pruebe estas variaciones en la línea de comandos para ver resultados diferentes:</span><span class="sxs-lookup"><span data-stu-id="8ee2a-138">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="8ee2a-139">Todos los argumentos después del delimitador `--` se pasan a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-139">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="8ee2a-140">Empaquetado de la herramienta</span><span class="sxs-lookup"><span data-stu-id="8ee2a-140">Package the tool</span></span>

<span data-ttu-id="8ee2a-141">Antes de que pueda empaquetar y distribuir la aplicación como una herramienta, debe modificar el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-141">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span> 

1. <span data-ttu-id="8ee2a-142">Abra el archivo *botsay-\<name>.csproj* y agregue tres nuevos nodos XML al final del nodo `<PropertyGroup>`:</span><span class="sxs-lookup"><span data-stu-id="8ee2a-142">Open the *botsay-\<name>.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="8ee2a-143">`<ToolCommandName>` es un elemento opcional que especifica el comando que invocará a la herramienta una vez instalada.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-143">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="8ee2a-144">Si no se proporciona este elemento, el nombre de comando para la herramienta es el nombre del archivo de proyecto sin la extensión *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-144">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="8ee2a-145">`<PackageOutputPath>` es un elemento opcional que determina dónde se generará el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-145">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="8ee2a-146">El paquete NuGet es el que la CLI de .NET Core utiliza para instalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-146">The NuGet package is what the .NET Core CLI uses to install your tool.</span></span>

   <span data-ttu-id="8ee2a-147">El archivo del proyecto debe ser similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8ee2a-147">The project file now looks like the following example:</span></span>

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

1. <span data-ttu-id="8ee2a-148">Cree un paquete NuGet ejecutando el comando [dotnet pack](dotnet-pack.md):</span><span class="sxs-lookup"><span data-stu-id="8ee2a-148">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="8ee2a-149">El archivo *botsay-\<name>.1.0.0.nupkg* se crea en la carpeta identificada por el valor `<PackageOutputPath>` desde el archivo *botsay-\<name>.csproj*, que en este ejemplo es la carpeta *./nupkg*.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-149">The *botsay-\<name>.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *botsay-\<name>.csproj* file, which in this example is the *./nupkg* folder.</span></span>
  
   <span data-ttu-id="8ee2a-150">Si quiere lanzar una herramienta públicamente, puede cargarla en `https://www.nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-150">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="8ee2a-151">Una vez que la herramienta está disponible en NuGet, los desarrolladores pueden instalar la herramienta mediante el comando [dotnet tool install](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="8ee2a-151">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="8ee2a-152">En este tutorial, se instalará el paquete directamente desde la carpeta local *nupkg*, por lo que no es necesario cargar el paquete en NuGet.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-152">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="8ee2a-153">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="8ee2a-153">Troubleshoot</span></span>

<span data-ttu-id="8ee2a-154">Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8ee2a-154">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ee2a-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ee2a-155">Next steps</span></span>

<span data-ttu-id="8ee2a-156">En este tutorial, ha creado una aplicación de consola y la ha empaquetado como una herramienta.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-156">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="8ee2a-157">Para aprender a usar la herramienta como una herramienta global, avance al siguiente tutorial.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-157">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8ee2a-158">Instalación y uso de una herramienta global</span><span class="sxs-lookup"><span data-stu-id="8ee2a-158">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="8ee2a-159">Si lo prefiere, puede omitir el tutorial de herramientas globales y pasar directamente al tutorial de herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="8ee2a-159">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8ee2a-160">Instalación y uso de una herramienta local</span><span class="sxs-lookup"><span data-stu-id="8ee2a-160">Install and use a local tool</span></span>](local-tools-how-to-use.md)

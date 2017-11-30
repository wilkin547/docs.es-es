---
title: "Implementación de aplicaciones de .NET Core con herramientas de la CLI"
description: "Obtenga información sobre la implementación de aplicaciones de .NET Core con herramientas de la interfaz de la línea de comandos (CLI)"
keywords: ".NET, .NET Core, implementación de .NET Core"
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 82ebe16d-5e1c-46cc-91e8-71974296429c
ms.openlocfilehash: fc7a40667c9b0a623bb0ebdf4ad60783fa58e6c5
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="8d9fe-104">Implementación de aplicaciones de .NET Core con herramientas de la interfaz de la línea de comandos (CLI)</span><span class="sxs-lookup"><span data-stu-id="8d9fe-104">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="8d9fe-105">Puede implementar una aplicación de .NET Core como una *implementación dependiente de la plataforma*, que incluye los archivos binarios de aplicación pero depende de la presencia de .NET Core en el sistema de destino, o como una *implementación independiente*, que incluye la aplicación y los archivos binarios de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-105">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="8d9fe-106">Para obtener información general, vea [Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="8d9fe-106">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="8d9fe-107">En las secciones siguientes se muestra cómo usar las [herramientas de la interfaz de la línea de comandos de .NET Core](../tools/index.md) para crear los siguientes tipos de implementaciones:</span><span class="sxs-lookup"><span data-stu-id="8d9fe-107">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="8d9fe-108">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="8d9fe-108">Framework-dependent deployment</span></span>
- <span data-ttu-id="8d9fe-109">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="8d9fe-109">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="8d9fe-110">Implementación autocontenida</span><span class="sxs-lookup"><span data-stu-id="8d9fe-110">Self-contained deployment</span></span>
- <span data-ttu-id="8d9fe-111">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="8d9fe-111">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="8d9fe-112">Cuando se trabaja desde la línea de comandos, puede usar un programa editor de su elección.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-112">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="8d9fe-113">Si el programa editor es [Visual Studio Code](https://code.visualstudio.com), puede abrir una consola de comandos dentro del entorno de Visual Studio Code seleccionando **Vista** > **Terminal integrado**.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-113">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="8d9fe-114">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="8d9fe-114">Framework-dependent deployment</span></span>

<span data-ttu-id="8d9fe-115">La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-115">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="8d9fe-116">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-116">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="8d9fe-117">Crear un directorio de proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-117">Create a project directory.</span></span>

   <span data-ttu-id="8d9fe-118">Cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-118">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="8d9fe-119">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-119">Create the project.</span></span>

   <span data-ttu-id="8d9fe-120">Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-120">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="8d9fe-121">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-121">Add the application's source code.</span></span>

   <span data-ttu-id="8d9fe-122">Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-122">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="8d9fe-123">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-123">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="8d9fe-124">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-124">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="8d9fe-125">Actualizar las herramientas y las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-125">Update the project's dependencies and tools.</span></span>
 
   <span data-ttu-id="8d9fe-126">Ejecute el [dotnet restauración](../tools/dotnet-restore.md) ([Véase la nota](#dotnet-restore-note)) comando para restaurar las dependencias especificadas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-126">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="8d9fe-127">Crear una versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-127">Create a Debug build of your app.</span></span>

   <span data-ttu-id="8d9fe-128">Use el comando [dotnet build](../tools/dotnet-build.md) para compilar la aplicación o el comando [dotnet run](../tools/dotnet-run.md) para compilarla y ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-128">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="8d9fe-129">Implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-129">Deploy your app.</span></span>

   <span data-ttu-id="8d9fe-130">Después de depurar y probar el programa, cree la implementación mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d9fe-130">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   <span data-ttu-id="8d9fe-131">Con esto se crea una versión (en lugar de una depuración) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-131">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="8d9fe-132">Los archivos resultantes se colocan en un directorio denominado *publish* que se encuentra en un subdirectorio del directorio *bin* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-132">The resulting files are placed in a directory named *publish* that's in a subdirectory of your project's *bin* directory.</span></span>

<span data-ttu-id="8d9fe-133">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-133">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="8d9fe-134">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-134">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="8d9fe-135">Puede decidir no distribuirlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-135">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="8d9fe-136">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-136">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="8d9fe-137">El conjunto completo de archivos de la aplicación se puede implementar del modo que quiera.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-137">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="8d9fe-138">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-138">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="8d9fe-139">Una vez instalados, los usuarios pueden ejecutar la aplicación mediante el comando `dotnet` y proporcionando el nombre de archivo, como `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="8d9fe-140">Además de los archivos binarios de la aplicación, el instalador también debe empaquetar el instalador de marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="8d9fe-141">La instalación del marco compartido requiere acceso raíz o de administrador.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="8d9fe-142">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="8d9fe-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="8d9fe-143">La implementación de una implementación dependiente de la plataforma con una o más dependencias de terceros requiere que esas dependencias estén disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="8d9fe-144">Se requieren dos pasos adicionales antes de poder ejecutar el `dotnet restore` ([Véase la nota](#dotnet-restore-note)) comando:</span><span class="sxs-lookup"><span data-stu-id="8d9fe-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="8d9fe-145">Agregue referencias a las bibliotecas de terceros requeridas a la sección `<ItemGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="8d9fe-146">La siguiente sección `<ItemGroup>` contiene una dependencia de [Json.NET](http://www.newtonsoft.com/json) como biblioteca de terceros:</span><span class="sxs-lookup"><span data-stu-id="8d9fe-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="8d9fe-147">Si no lo ha hecho ya, descargue el paquete de NuGet que contiene la dependencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="8d9fe-148">Para descargar el paquete, ejecute el `dotnet restore` ([Véase la nota](#dotnet-restore-note)) comando después de agregar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="8d9fe-149">Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="8d9fe-150">Tenga en cuenta que una implementación dependiente de la plataforma con dependencias de terceros solo será tan portátil como sus dependencias de terceros.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="8d9fe-151">Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se puede portar a sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="8d9fe-152">Esto ocurre si la dependencia de terceros propiamente dicha depende del código nativo.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="8d9fe-153">Un buen ejemplo de esto es [el servidor Kestrel](/aspnet/core/fundamentals/servers/kestrel), que requiere una dependencia nativa de [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="8d9fe-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="8d9fe-154">Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contiene una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md) que admita la dependencia nativa (y que exista en su paquete de NuGet).</span><span class="sxs-lookup"><span data-stu-id="8d9fe-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <span data-ttu-id="8d9fe-155"><a name="simpleSelf"></a> Implementación independiente sin dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="8d9fe-155"><a name="simpleSelf"></a> Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="8d9fe-156">La implementación de una implementación independiente sin dependencias de terceros implica crear el proyecto, modificar el archivo *csproj* y compilar, probar y publicar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="8d9fe-157">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="8d9fe-158">En el ejemplo se muestra cómo crear una implementación independiente mediante la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="8d9fe-159">Crear un directorio para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-159">Create a directory for the project.</span></span>

   <span data-ttu-id="8d9fe-160">Cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="8d9fe-161">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-161">Create the project.</span></span>

   <span data-ttu-id="8d9fe-162">Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="8d9fe-163">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-163">Add the application's source code.</span></span>

   <span data-ttu-id="8d9fe-164">Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="8d9fe-165">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="8d9fe-166">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="8d9fe-167">Definir las plataformas de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="8d9fe-168">Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo *csproj* que defina las plataformas a las que se destina la aplicación y especifique el identificador en tiempo de ejecución (RID) de cada una.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="8d9fe-169">Tenga en cuenta que también debe agregar un punto y coma para separar los RID.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="8d9fe-170">Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8d9fe-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="8d9fe-171">Por ejemplo, la siguiente sección `<PropertyGroup>` indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="8d9fe-172">Tenga en cuenta que el elemento `<RuntimeIdentifiers>` puede aparecer en cualquier `<PropertyGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="8d9fe-173">Más adelante en esta sección aparece un ejemplo completo del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="8d9fe-174">Actualizar las herramientas y las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="8d9fe-175">Ejecute el [dotnet restauración](../tools/dotnet-restore.md) ([Véase la nota](#dotnet-restore-note)) comando para restaurar las dependencias especificadas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="8d9fe-176">Crear una versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-176">Create a Debug build of your app.</span></span>

   <span data-ttu-id="8d9fe-177">Desde la línea de comandos, use el comando [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="8d9fe-177">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="8d9fe-178">Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-178">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="8d9fe-179">Use el comando `dotnet publish` para las dos plataformas de destino como sigue:</span><span class="sxs-lookup"><span data-stu-id="8d9fe-179">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="8d9fe-180">Se crea una versión (en lugar de una depuración) de la aplicación para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-180">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="8d9fe-181">Los archivos resultantes se colocan en un subdirectorio denominado *publish* que se encuentra en un subdirectorio del subdirectorio *.\bin\Release\netcoreapp1.1\<identificador_TiempoDeEjecución>* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-181">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp1.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="8d9fe-182">Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-182">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="8d9fe-183">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-183">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="8d9fe-184">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-184">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="8d9fe-185">Puede decidir no empaquetarlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-185">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="8d9fe-186">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-186">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="8d9fe-187">Implemente los archivos publicados de la forma que quiera.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-187">Deploy the published files in any way you like.</span></span> <span data-ttu-id="8d9fe-188">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-188">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="8d9fe-189">A continuación se muestra el archivo *csproj* completo para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-189">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="8d9fe-190">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="8d9fe-190">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="8d9fe-191">Implementar una implementación independiente con una o varias dependencias de terceros implica agregar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-191">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="8d9fe-192">Se requieren dos pasos adicionales antes de poder ejecutar el `dotnet restore` ([Véase la nota](#dotnet-restore-note)) comando:</span><span class="sxs-lookup"><span data-stu-id="8d9fe-192">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="8d9fe-193">Agregue referencias a las bibliotecas de terceros a la sección `<ItemGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-193">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="8d9fe-194">La siguiente sección `<ItemGroup>` usa Json.NET como biblioteca de terceros.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-194">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="8d9fe-195">Si aún no lo ha hecho, descargue el paquete de NuGet que contiene la dependencia de terceros en el sistema.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-195">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="8d9fe-196">Para disponer de la dependencia a la aplicación, ejecute el `dotnet restore` ([Véase la nota](#dotnet-restore-note)) comando después de agregar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-196">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="8d9fe-197">Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-197">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="8d9fe-198">A continuación se muestra el archivo *csproj* completo de este proyecto:</span><span class="sxs-lookup"><span data-stu-id="8d9fe-198">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="8d9fe-199">Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-199">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="8d9fe-200">No se requieren las bibliotecas de terceros en el sistema en el que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-200">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="8d9fe-201">Tenga en cuenta que solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-201">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="8d9fe-202">Esto es similar a tener dependencias de terceros con dependencias nativas en una implementación dependiente de la plataforma, donde las dependencias nativas deben ser compatibles con la plataforma en la que se implementa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d9fe-202">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

# <a name="see-also"></a><span data-ttu-id="8d9fe-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d9fe-203">See also</span></span>

<span data-ttu-id="8d9fe-204">[Implementación de aplicaciones .NET Core](index.md) </span><span class="sxs-lookup"><span data-stu-id="8d9fe-204">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="8d9fe-205">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="8d9fe-205">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   


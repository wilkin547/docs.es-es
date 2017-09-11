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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 005355868eefdbf21e3107f6db5230d7952276b2
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="35bb3-104">Implementación de aplicaciones de .NET Core con herramientas de la interfaz de la línea de comandos (CLI)</span><span class="sxs-lookup"><span data-stu-id="35bb3-104">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="35bb3-105">Puede implementar una aplicación de .NET Core como una *implementación dependiente de la plataforma*, que incluye los archivos binarios de aplicación pero depende de la presencia de .NET Core en el sistema de destino, o como una *implementación independiente*, que incluye la aplicación y los archivos binarios de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="35bb3-105">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="35bb3-106">Para obtener información general, vea [Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="35bb3-106">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="35bb3-107">En las secciones siguientes se muestra cómo usar las [herramientas de la interfaz de la línea de comandos de .NET Core](../tools/index.md) para crear los siguientes tipos de implementaciones:</span><span class="sxs-lookup"><span data-stu-id="35bb3-107">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="35bb3-108">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="35bb3-108">Framework-dependent deployment</span></span>
- <span data-ttu-id="35bb3-109">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="35bb3-109">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="35bb3-110">Implementación autocontenida</span><span class="sxs-lookup"><span data-stu-id="35bb3-110">Self-contained deployment</span></span>
- <span data-ttu-id="35bb3-111">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="35bb3-111">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="35bb3-112">Cuando se trabaja desde la línea de comandos, puede usar un programa editor de su elección.</span><span class="sxs-lookup"><span data-stu-id="35bb3-112">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="35bb3-113">Si el programa editor es [Visual Studio Code](https://code.visualstudio.com), puede abrir una consola de comandos dentro del entorno de Visual Studio Code seleccionando **Vista** > **Terminal integrado**.</span><span class="sxs-lookup"><span data-stu-id="35bb3-113">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="35bb3-114">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="35bb3-114">Framework-dependent deployment</span></span>

<span data-ttu-id="35bb3-115">La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-115">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="35bb3-116">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="35bb3-116">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="35bb3-117">Crear un directorio de proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-117">Create a project directory.</span></span>

   <span data-ttu-id="35bb3-118">Cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="35bb3-118">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="35bb3-119">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-119">Create the project.</span></span>

   <span data-ttu-id="35bb3-120">Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="35bb3-120">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="35bb3-121">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-121">Add the application's source code.</span></span>

   <span data-ttu-id="35bb3-122">Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="35bb3-122">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="35bb3-123">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="35bb3-123">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="35bb3-124">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="35bb3-124">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="35bb3-125">[!code-cs[implementación1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="35bb3-125">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="35bb3-126">Actualizar las herramientas y las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-126">Update the project's dependencies and tools.</span></span>
 
   <span data-ttu-id="35bb3-127">Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) para restaurar las dependencias especificadas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-127">Run the [dotnet restore](../tools/dotnet-restore.md) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="35bb3-128">Crear una versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-128">Create a Debug build of your app.</span></span>

   <span data-ttu-id="35bb3-129">Use el comando [dotnet build](../tools/dotnet-build.md) para compilar la aplicación o el comando [dotnet run](../tools/dotnet-run.md) para compilarla y ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="35bb3-129">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="35bb3-130">Implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-130">Deploy your app.</span></span>

   <span data-ttu-id="35bb3-131">Después de depurar y probar el programa, cree la implementación mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="35bb3-131">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   <span data-ttu-id="35bb3-132">Con esto se crea una versión (en lugar de una depuración) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-132">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="35bb3-133">Los archivos resultantes se colocan en un directorio denominado *publish* que se encuentra en un subdirectorio del directorio *bin* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-133">The resulting files are placed in a directory named *publish* that's in a subdirectory of your project's *bin* directory.</span></span>

<span data-ttu-id="35bb3-134">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-134">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="35bb3-135">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="35bb3-135">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="35bb3-136">Puede decidir no distribuirlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-136">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="35bb3-137">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-137">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="35bb3-138">El conjunto completo de archivos de la aplicación se puede implementar del modo que quiera.</span><span class="sxs-lookup"><span data-stu-id="35bb3-138">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="35bb3-139">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="35bb3-139">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="35bb3-140">Una vez instalados, los usuarios pueden ejecutar la aplicación mediante el comando `dotnet` y proporcionando el nombre de archivo, como `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="35bb3-140">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="35bb3-141">Además de los archivos binarios de la aplicación, el instalador también debe empaquetar el instalador de marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-141">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="35bb3-142">La instalación del marco compartido requiere acceso raíz o de administrador.</span><span class="sxs-lookup"><span data-stu-id="35bb3-142">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="35bb3-143">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="35bb3-143">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="35bb3-144">La implementación de una implementación dependiente de la plataforma con una o más dependencias de terceros requiere que esas dependencias estén disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-144">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="35bb3-145">Se requieren dos pasos adicionales antes de poder ejecutar el comando `dotnet restore`:</span><span class="sxs-lookup"><span data-stu-id="35bb3-145">Two additional steps are required before you can run the `dotnet restore` command:</span></span>

1. <span data-ttu-id="35bb3-146">Agregue referencias a las bibliotecas de terceros requeridas a la sección `<ItemGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="35bb3-146">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="35bb3-147">La siguiente sección `<ItemGroup>` contiene una dependencia de [Json.NET](http://www.newtonsoft.com/json) como biblioteca de terceros:</span><span class="sxs-lookup"><span data-stu-id="35bb3-147">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="35bb3-148">Si no lo ha hecho ya, descargue el paquete de NuGet que contiene la dependencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="35bb3-148">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="35bb3-149">Para descargar el paquete, ejecute el comando `dotnet restore` después de agregar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="35bb3-149">To download the package, execute the `dotnet restore` command after adding the dependency.</span></span> <span data-ttu-id="35bb3-150">Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.</span><span class="sxs-lookup"><span data-stu-id="35bb3-150">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="35bb3-151">Tenga en cuenta que una implementación dependiente de la plataforma con dependencias de terceros solo será tan portátil como sus dependencias de terceros.</span><span class="sxs-lookup"><span data-stu-id="35bb3-151">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="35bb3-152">Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se puede portar a sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="35bb3-152">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="35bb3-153">Esto ocurre si la dependencia de terceros propiamente dicha depende del código nativo.</span><span class="sxs-lookup"><span data-stu-id="35bb3-153">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="35bb3-154">Un buen ejemplo de esto es [el servidor Kestrel](/aspnet/core/fundamentals/servers/kestrel), que requiere una dependencia nativa de [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="35bb3-154">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="35bb3-155">Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contiene una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md#what-are-rids) que admita la dependencia nativa (y que exista en su paquete de NuGet).</span><span class="sxs-lookup"><span data-stu-id="35bb3-155">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md#what-are-rids) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <span data-ttu-id="35bb3-156"><a name="simpleSelf"></a> Implementación independiente sin dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="35bb3-156"><a name="simpleSelf"></a> Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="35bb3-157">La implementación de una implementación independiente sin dependencias de terceros implica crear el proyecto, modificar el archivo *csproj* y compilar, probar y publicar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-157">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="35bb3-158">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="35bb3-158">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="35bb3-159">En el ejemplo se muestra cómo crear una implementación independiente mediante la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="35bb3-159">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="35bb3-160">Crear un directorio para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-160">Create a directory for the project.</span></span>

   <span data-ttu-id="35bb3-161">Cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="35bb3-161">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="35bb3-162">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-162">Create the project.</span></span>

   <span data-ttu-id="35bb3-163">Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="35bb3-163">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="35bb3-164">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-164">Add the application's source code.</span></span>

   <span data-ttu-id="35bb3-165">Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="35bb3-165">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="35bb3-166">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="35bb3-166">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="35bb3-167">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="35bb3-167">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="35bb3-168">[!code-cs[implementación1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="35bb3-168">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="35bb3-169">Definir las plataformas de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-169">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="35bb3-170">Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo *csproj* que defina las plataformas a las que se destina la aplicación y especifique el identificador en tiempo de ejecución (RID) de cada una.</span><span class="sxs-lookup"><span data-stu-id="35bb3-170">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="35bb3-171">Tenga en cuenta que también debe agregar un punto y coma para separar los RID.</span><span class="sxs-lookup"><span data-stu-id="35bb3-171">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="35bb3-172">Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="35bb3-172">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="35bb3-173">Por ejemplo, la siguiente sección `<PropertyGroup>` indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="35bb3-173">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="35bb3-174">Tenga en cuenta que el elemento `<RuntimeIdentifiers>` puede aparecer en cualquier `<PropertyGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="35bb3-174">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="35bb3-175">Más adelante en esta sección aparece un ejemplo completo del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="35bb3-175">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="35bb3-176">Actualizar las herramientas y las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-176">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="35bb3-177">Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) para restaurar las dependencias especificadas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-177">Run the [dotnet restore](../tools/dotnet-restore.md) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="35bb3-178">Crear una versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-178">Create a Debug build of your app.</span></span>

   <span data-ttu-id="35bb3-179">Desde la línea de comandos, use el comando [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="35bb3-179">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="35bb3-180">Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="35bb3-180">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="35bb3-181">Use el comando `dotnet publish` para las dos plataformas de destino como sigue:</span><span class="sxs-lookup"><span data-stu-id="35bb3-181">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="35bb3-182">Se crea una versión (en lugar de una depuración) de la aplicación para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="35bb3-182">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="35bb3-183">Los archivos resultantes se colocan en un subdirectorio denominado *publish* que se encuentra en un subdirectorio del subdirectorio *.\bin\Release\netcoreapp1.1\<identificador_TiempoDeEjecución>* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-183">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp1.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="35bb3-184">Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-184">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="35bb3-185">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-185">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="35bb3-186">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="35bb3-186">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="35bb3-187">Puede decidir no empaquetarlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-187">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="35bb3-188">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-188">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="35bb3-189">Implemente los archivos publicados de la forma que quiera.</span><span class="sxs-lookup"><span data-stu-id="35bb3-189">Deploy the published files in any way you like.</span></span> <span data-ttu-id="35bb3-190">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="35bb3-190">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="35bb3-191">A continuación se muestra el archivo *csproj* completo para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="35bb3-191">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="35bb3-192">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="35bb3-192">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="35bb3-193">Implementar una implementación independiente con una o varias dependencias de terceros implica agregar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="35bb3-193">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="35bb3-194">Se requieren dos pasos adicionales antes de poder ejecutar el comando `dotnet restore`:</span><span class="sxs-lookup"><span data-stu-id="35bb3-194">Two additional steps are required before you can run the `dotnet restore` command:</span></span>

1. <span data-ttu-id="35bb3-195">Agregue referencias a las bibliotecas de terceros a la sección `<ItemGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="35bb3-195">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="35bb3-196">La siguiente sección `<ItemGroup>` usa Json.NET como biblioteca de terceros.</span><span class="sxs-lookup"><span data-stu-id="35bb3-196">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="35bb3-197">Si aún no lo ha hecho, descargue el paquete de NuGet que contiene la dependencia de terceros en el sistema.</span><span class="sxs-lookup"><span data-stu-id="35bb3-197">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="35bb3-198">Para que la dependencia esté disponibles para la aplicación, ejecute el comando `dotnet restore` después de agregar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="35bb3-198">To make the dependency available to your app, execute the `dotnet restore` command after adding the dependency.</span></span> <span data-ttu-id="35bb3-199">Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.</span><span class="sxs-lookup"><span data-stu-id="35bb3-199">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="35bb3-200">A continuación se muestra el archivo *csproj* completo de este proyecto:</span><span class="sxs-lookup"><span data-stu-id="35bb3-200">The following is the complete *csproj* file for this project:</span></span>

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

<span data-ttu-id="35bb3-201">Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-201">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="35bb3-202">No se requieren las bibliotecas de terceros en el sistema en el que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-202">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="35bb3-203">Tenga en cuenta que solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="35bb3-203">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="35bb3-204">Esto es similar a tener dependencias de terceros con dependencias nativas en una implementación dependiente de la plataforma, donde las dependencias nativas deben ser compatibles con la plataforma en la que se implementa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35bb3-204">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

# <a name="see-also"></a><span data-ttu-id="35bb3-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="35bb3-205">See also</span></span>

<span data-ttu-id="35bb3-206">[Implementación de aplicaciones .NET Core](index.md) </span><span class="sxs-lookup"><span data-stu-id="35bb3-206">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="35bb3-207">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="35bb3-207">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   


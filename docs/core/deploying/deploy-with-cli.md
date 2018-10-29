---
title: Implementación de aplicaciones de .NET Core con herramientas de la CLI
description: Obtenga información sobre la implementación de aplicaciones de .NET Core con herramientas de la interfaz de la línea de comandos (CLI)
author: rpetrusha
ms.author: ronpet
ms.date: 09/05/2018
dev_langs:
- csharp
- vb
ms.openlocfilehash: 6c0eb82b6be5d65c70287dd601bb97868af1c943
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454454"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="66482-103">Implementación de aplicaciones de .NET Core con herramientas de la interfaz de la línea de comandos (CLI)</span><span class="sxs-lookup"><span data-stu-id="66482-103">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="66482-104">Puede implementar una aplicación de .NET Core como una *implementación dependiente de la plataforma*, que incluye los archivos binarios de aplicación pero depende de la presencia de .NET Core en el sistema de destino, o como una *implementación independiente*, que incluye la aplicación y los archivos binarios de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="66482-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="66482-105">Para obtener información general, vea [Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="66482-105">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="66482-106">En las secciones siguientes se muestra cómo usar las [herramientas de la interfaz de la línea de comandos de .NET Core](../tools/index.md) para crear los siguientes tipos de implementaciones:</span><span class="sxs-lookup"><span data-stu-id="66482-106">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="66482-107">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="66482-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="66482-108">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="66482-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="66482-109">Implementación autocontenida</span><span class="sxs-lookup"><span data-stu-id="66482-109">Self-contained deployment</span></span>
- <span data-ttu-id="66482-110">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="66482-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="66482-111">Cuando se trabaja desde la línea de comandos, puede usar un programa editor de su elección.</span><span class="sxs-lookup"><span data-stu-id="66482-111">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="66482-112">Si el programa editor es [Visual Studio Code](https://code.visualstudio.com), puede abrir una consola de comandos dentro del entorno de Visual Studio Code seleccionando **Vista** > **Terminal integrado**.</span><span class="sxs-lookup"><span data-stu-id="66482-112">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="66482-113">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="66482-113">Framework-dependent deployment</span></span>

<span data-ttu-id="66482-114">La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="66482-115">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="66482-115">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="66482-116">Crear un directorio de proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-116">Create a project directory.</span></span>

   <span data-ttu-id="66482-117">Cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="66482-117">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="66482-118">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-118">Create the project.</span></span>

   <span data-ttu-id="66482-119">Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# o [dotnet new console -lang vb](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de Visual Basic en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="66482-119">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project or [dotnet new console -lang vb](../tools/dotnet-new.md) to create a new Visual Basic console project in that directory.</span></span>

1. <span data-ttu-id="66482-120">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-120">Add the application's source code.</span></span>

   <span data-ttu-id="66482-121">Abra el archivo *Program.cs* o *Program.vb* en el editor y reemplace el código generado automáticamente por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="66482-121">Open the *Program.cs* or *Program.vb* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="66482-122">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="66482-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="66482-123">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="66482-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="66482-124">Actualizar las herramientas y las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-124">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="66482-125">Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias especificadas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-125">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="66482-126">Crear una versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="66482-127">Use el comando [dotnet build](../tools/dotnet-build.md) para compilar la aplicación o el comando [dotnet run](../tools/dotnet-run.md) para compilarla y ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="66482-127">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="66482-128">Implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-128">Deploy your app.</span></span>

   <span data-ttu-id="66482-129">Después de depurar y probar el programa, cree la implementación mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="66482-129">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp2.1 -c Release
      ```
   <span data-ttu-id="66482-130">Con esto se crea una versión (en lugar de una depuración) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-130">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="66482-131">Los archivos resultantes se colocan en un directorio denominado *publish* que se encuentra en un subdirectorio del directorio *bin* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-131">The resulting files are placed in a directory named *publish*      that's in a subdirectory of your project's *bin* directory.</span></span>

   <span data-ttu-id="66482-132">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-132">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="66482-133">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="66482-133">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="66482-134">Puede decidir no distribuirlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-134">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="66482-135">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-135">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

   <span data-ttu-id="66482-136">El conjunto completo de archivos de la aplicación se puede implementar del modo que quiera.</span><span class="sxs-lookup"><span data-stu-id="66482-136">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="66482-137">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="66482-137">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

1. <span data-ttu-id="66482-138">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="66482-138">Run your app</span></span>

   <span data-ttu-id="66482-139">Una vez instalados, los usuarios pueden ejecutar la aplicación mediante el comando `dotnet` y proporcionando el nombre de archivo, como `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="66482-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

   <span data-ttu-id="66482-140">Además de los archivos binarios de la aplicación, el instalador también debe empaquetar el instalador de marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="66482-141">La instalación del marco compartido requiere acceso raíz o de administrador.</span><span class="sxs-lookup"><span data-stu-id="66482-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="66482-142">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="66482-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="66482-143">La implementación de una implementación dependiente de la plataforma con una o más dependencias de terceros requiere que esas dependencias estén disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="66482-144">Para poder ejecutar el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) son necesarios otros dos pasos:</span><span class="sxs-lookup"><span data-stu-id="66482-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="66482-145">Agregue referencias a las bibliotecas de terceros requeridas a la sección `<ItemGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="66482-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="66482-146">La siguiente sección `<ItemGroup>` contiene una dependencia de [Json.NET](https://www.newtonsoft.com/json) como biblioteca de terceros:</span><span class="sxs-lookup"><span data-stu-id="66482-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](https://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="66482-147">Si no lo ha hecho ya, descargue el paquete de NuGet que contiene la dependencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="66482-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="66482-148">Para descargar el paquete, ejecute el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) después de agregar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="66482-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="66482-149">Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.</span><span class="sxs-lookup"><span data-stu-id="66482-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="66482-150">Tenga en cuenta que una implementación dependiente de la plataforma con dependencias de terceros solo será tan portátil como sus dependencias de terceros.</span><span class="sxs-lookup"><span data-stu-id="66482-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="66482-151">Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se puede portar a sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="66482-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="66482-152">Esto ocurre si la dependencia de terceros propiamente dicha depende del código nativo.</span><span class="sxs-lookup"><span data-stu-id="66482-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="66482-153">Un buen ejemplo de esto es [el servidor Kestrel](/aspnet/core/fundamentals/servers/kestrel), que requiere una dependencia nativa de [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="66482-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="66482-154">Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contiene una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md) que admita la dependencia nativa (y que exista en su paquete de NuGet).</span><span class="sxs-lookup"><span data-stu-id="66482-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a> <span data-ttu-id="66482-155">Implementación independiente sin dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="66482-155">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="66482-156">La implementación de una implementación independiente sin dependencias de terceros implica crear el proyecto, modificar el archivo *csproj* y compilar, probar y publicar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="66482-157">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="66482-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="66482-158">En el ejemplo se muestra cómo crear una implementación independiente mediante la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="66482-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="66482-159">Crear un directorio para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-159">Create a directory for the project.</span></span>

   <span data-ttu-id="66482-160">Cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="66482-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="66482-161">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-161">Create the project.</span></span>

   <span data-ttu-id="66482-162">Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="66482-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="66482-163">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-163">Add the application's source code.</span></span>

   <span data-ttu-id="66482-164">Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="66482-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="66482-165">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="66482-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="66482-166">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="66482-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]
1. <span data-ttu-id="66482-167">Definir las plataformas de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="66482-168">Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo *csproj* que defina las plataformas a las que se destina la aplicación y especifique el identificador en tiempo de ejecución (RID) de cada una.</span><span class="sxs-lookup"><span data-stu-id="66482-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="66482-169">Tenga en cuenta que también debe agregar un punto y coma para separar los RID.</span><span class="sxs-lookup"><span data-stu-id="66482-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="66482-170">Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="66482-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="66482-171">Por ejemplo, la siguiente sección `<PropertyGroup>` indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="66482-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="66482-172">Tenga en cuenta que el elemento `<RuntimeIdentifiers>` puede aparecer en cualquier `<PropertyGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="66482-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="66482-173">Más adelante en esta sección aparece un ejemplo completo del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="66482-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="66482-174">Actualizar las herramientas y las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="66482-175">Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias especificadas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="66482-176">Determine si quiere usar el modo de globalización invariable.</span><span class="sxs-lookup"><span data-stu-id="66482-176">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="66482-177">Especialmente si la aplicación es para Linux, puede reducir el tamaño total de la implementación si aprovecha las ventajas del [modo de globalización invariable](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="66482-177">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span> <span data-ttu-id="66482-178">El modo de globalización invariable es útil para aquellas aplicaciones que no son globales y que pueden usar las convenciones de formato, las convenciones de mayúsculas y minúsculas y el criterio de ordenación y la comparación de cadenas de la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture).</span><span class="sxs-lookup"><span data-stu-id="66482-178">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="66482-179">Para habilitar el modo invariable, haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Editar SCD.csproj** o **Editar SCD.vbproj**.</span><span class="sxs-lookup"><span data-stu-id="66482-179">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="66482-180">Luego agregue las siguientes líneas resaltadas al archivo:</span><span class="sxs-lookup"><span data-stu-id="66482-180">Then add the following highlighted lines to the file:</span></span>

 [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj)]

1. <span data-ttu-id="66482-181">Crear una versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-181">Create a Debug build of your app.</span></span>

   <span data-ttu-id="66482-182">Desde la línea de comandos, use el comando [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="66482-182">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="66482-183">Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="66482-183">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="66482-184">Use el comando `dotnet publish` para las dos plataformas de destino como sigue:</span><span class="sxs-lookup"><span data-stu-id="66482-184">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="66482-185">Se crea una versión (en lugar de una depuración) de la aplicación para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="66482-185">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="66482-186">Los archivos resultantes se colocan en un subdirectorio denominado *publish* que se encuentra en un subdirectorio del subdirectorio *.\bin\Release\netcoreapp2.1\<runtime_identifier>* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-186">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp2.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="66482-187">Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-187">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="66482-188">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-188">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="66482-189">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="66482-189">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="66482-190">Puede decidir no empaquetarlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-190">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="66482-191">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-191">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="66482-192">Implemente los archivos publicados de la forma que quiera.</span><span class="sxs-lookup"><span data-stu-id="66482-192">Deploy the published files in any way you like.</span></span> <span data-ttu-id="66482-193">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="66482-193">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="66482-194">A continuación se muestra el archivo *csproj* completo para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="66482-194">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="66482-195">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="66482-195">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="66482-196">Implementar una implementación independiente con una o varias dependencias de terceros implica agregar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="66482-196">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="66482-197">Para poder ejecutar el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) son necesarios otros dos pasos:</span><span class="sxs-lookup"><span data-stu-id="66482-197">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="66482-198">Agregue referencias a las bibliotecas de terceros a la sección `<ItemGroup>` del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="66482-198">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="66482-199">La siguiente sección `<ItemGroup>` usa Json.NET como biblioteca de terceros.</span><span class="sxs-lookup"><span data-stu-id="66482-199">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="66482-200">Si aún no lo ha hecho, descargue el paquete de NuGet que contiene la dependencia de terceros en el sistema.</span><span class="sxs-lookup"><span data-stu-id="66482-200">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="66482-201">Para que la dependencia esté disponible para la aplicación, ejecute el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) después de agregar la dependencia.</span><span class="sxs-lookup"><span data-stu-id="66482-201">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="66482-202">Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.</span><span class="sxs-lookup"><span data-stu-id="66482-202">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="66482-203">A continuación se muestra el archivo *csproj* completo de este proyecto:</span><span class="sxs-lookup"><span data-stu-id="66482-203">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="66482-204">Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-204">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="66482-205">No se requieren las bibliotecas de terceros en el sistema en el que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-205">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="66482-206">Tenga en cuenta que solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="66482-206">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="66482-207">Esto es similar a tener dependencias de terceros con dependencias nativas en una implementación dependiente de la plataforma, donde las dependencias nativas deben ser compatibles con la plataforma en la que se implementa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66482-207">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

## <a name="see-also"></a><span data-ttu-id="66482-208">Vea también</span><span class="sxs-lookup"><span data-stu-id="66482-208">See also</span></span>

* [<span data-ttu-id="66482-209">Implementación de aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="66482-209">.NET Core Application Deployment</span></span>](index.md)
* [<span data-ttu-id="66482-210">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="66482-210">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

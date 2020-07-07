---
title: Implementación de aplicaciones de .NET Core con Visual Studio
description: Aprenda a implementar una aplicación de .NET Core con Visual Studio.
ms.date: 09/03/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 7a4ffd5b1b58e6ea7fd46c676e139b77a126aa2b
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803032"
---
# <a name="deploy-net-core-apps-with-visual-studio"></a><span data-ttu-id="6fc05-103">Implementación de aplicaciones de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6fc05-103">Deploy .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="6fc05-104">Puede implementar una aplicación de .NET Core como una *implementación dependiente de la plataforma*, que incluye los archivos binarios de la aplicación pero depende de la presencia de .NET Core en el sistema de destino, o como una *implementación independiente*, que incluye la aplicación y los archivos binarios de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6fc05-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and .NET Core binaries.</span></span> <span data-ttu-id="6fc05-105">Para obtener información general sobre la implementación de aplicaciones de NET Core, vea [Implementación de aplicaciones .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="6fc05-105">For an overview of .NET Core application deployment, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="6fc05-106">En las secciones siguientes se muestra cómo usar Microsoft Visual Studio para crear los siguientes tipos de implementaciones:</span><span class="sxs-lookup"><span data-stu-id="6fc05-106">The following sections show how to use Microsoft Visual Studio to create the following kinds of deployments:</span></span>

- <span data-ttu-id="6fc05-107">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="6fc05-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="6fc05-108">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="6fc05-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="6fc05-109">Implementación autocontenida</span><span class="sxs-lookup"><span data-stu-id="6fc05-109">Self-contained deployment</span></span>
- <span data-ttu-id="6fc05-110">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="6fc05-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="6fc05-111">Para obtener información sobre el uso de Visual Studio para desarrollar aplicaciones de .NET Core, vea [Dependencias y requisitos de .NET Core](../install/dependencies.md?pivots=os-windows) .</span><span class="sxs-lookup"><span data-stu-id="6fc05-111">For information on using Visual Studio to develop .NET Core applications, see [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-windows).</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="6fc05-112">Implementación dependiente de marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="6fc05-112">Framework-dependent deployment</span></span>

<span data-ttu-id="6fc05-113">La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-113">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="6fc05-114">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="6fc05-114">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="6fc05-115">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fc05-115">Create the project.</span></span>

   <span data-ttu-id="6fc05-116">Seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-116">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="6fc05-117">En el cuadro de diálogo **Nuevo proyecto**, expanda las categorías de proyecto del lenguaje (C# o Visual Basic) en el panel de tipos de proyecto **instalados**, elija **.NET Core** y luego seleccione la plantilla **Aplicación de consola (.NET Core)** en el panel central.</span><span class="sxs-lookup"><span data-stu-id="6fc05-117">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="6fc05-118">Escriba un nombre de proyecto, como "FDD", en el cuadro de texto **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-118">Enter a project name, such as "FDD", in the **Name** text box.</span></span> <span data-ttu-id="6fc05-119">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-119">Select the **OK** button.</span></span>

1. <span data-ttu-id="6fc05-120">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-120">Add the application's source code.</span></span>

   <span data-ttu-id="6fc05-121">Abra el archivo *Program.cs* o *Program.vb* en el editor y reemplace el código generado automáticamente por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fc05-121">Open the *Program.cs* or *Program.vb* file in the editor and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="6fc05-122">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6fc05-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="6fc05-123">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="6fc05-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](./snippets/deploy-with-vs/csharp/deployment-example.cs)]
   [!code-vb[deployment#1](./snippets/deploy-with-vs/vb/deployment-example.vb)]

1. <span data-ttu-id="6fc05-124">Crear una versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-124">Create a Debug build of your app.</span></span>

   <span data-ttu-id="6fc05-125">Seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-125">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="6fc05-126">También puede compilar y ejecutar la versión de depuración de la aplicación seleccionando **Depurar** > **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-126">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="6fc05-127">Implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-127">Deploy your app.</span></span>

   <span data-ttu-id="6fc05-128">Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-128">After you've debugged and tested the program, create the files to be deployed with your app.</span></span> <span data-ttu-id="6fc05-129">Para publicar desde Visual Studio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6fc05-129">To publish from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="6fc05-130">Cambie la configuración de la solución de **Depurar** a **Versión** en la barra de herramientas para compilar una compilación de versión (en lugar de depuración) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-130">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="6fc05-131">Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-131">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="6fc05-132">En la pestaña **Publicar**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-132">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="6fc05-133">Visual Studio escribe los archivos que componen la aplicación en el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="6fc05-133">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="6fc05-134">La pestaña **Publicar** muestra ahora un solo perfil, **FolderProfile**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-134">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="6fc05-135">Los valores de configuración del perfil se muestran en la sección **Resumen** de la pestaña.</span><span class="sxs-lookup"><span data-stu-id="6fc05-135">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span>

   <span data-ttu-id="6fc05-136">Los archivos resultantes se colocan en un directorio denominado `Publish` en Windows y `publish` en sistemas Unix que está en un subdirectorio del subdirectorio *.\bin\release\netcoreapp2.1* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fc05-136">The resulting files are placed in a directory named `Publish` on Windows and `publish` on Unix systems that is in a subdirectory of your project's *.\bin\release\netcoreapp2.1* subdirectory.</span></span>

<span data-ttu-id="6fc05-137">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-137">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="6fc05-138">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="6fc05-138">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="6fc05-139">Puede decidir no empaquetarlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-139">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="6fc05-140">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-140">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="6fc05-141">Implemente el conjunto completo de archivos de la aplicación del modo que quiera.</span><span class="sxs-lookup"><span data-stu-id="6fc05-141">Deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="6fc05-142">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6fc05-142">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="6fc05-143">Una vez instalados, los usuarios pueden ejecutar la aplicación mediante el comando `dotnet` y proporcionando el nombre de archivo, como `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="6fc05-143">Once installed, users can then execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="6fc05-144">Además de los archivos binarios de la aplicación, el instalador también debe empaquetar el instalador de marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-144">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="6fc05-145">La instalación del marco compartido requiere acceso raíz o de administrador dado que implica a toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="6fc05-145">Installation of the shared framework requires Administrator/root access since it is machine-wide.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="6fc05-146">Implementación dependiente de marco de trabajo con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="6fc05-146">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="6fc05-147">La implementación de una implementación dependiente de la plataforma con una o más dependencias de terceros requiere que todas las dependencias estén disponibles para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fc05-147">Deploying a framework-dependent deployment with one or more third-party dependencies requires that any dependencies be available to your project.</span></span> <span data-ttu-id="6fc05-148">Se requieren los pasos adicionales siguientes antes de poder compilar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6fc05-148">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="6fc05-149">Use el **Administrador de paquetes NuGet** para agregar una referencia a un paquete de NuGet para el proyecto y, si el paquete todavía no está disponible en el sistema, instálelo.</span><span class="sxs-lookup"><span data-stu-id="6fc05-149">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="6fc05-150">Para abrir el administrador de paquetes, seleccione **Herramientas** > **Administrador de paquetes NuGet** > **Administrar paquetes NuGet para la solución**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-150">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="6fc05-151">Confirme que las dependencias de terceros (por ejemplo, `Newtonsoft.Json`) están instaladas en el sistema y, si no es así, instálelas.</span><span class="sxs-lookup"><span data-stu-id="6fc05-151">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="6fc05-152">La pestaña **Instalado** enumera los paquetes de NuGet instalados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="6fc05-152">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="6fc05-153">Si `Newtonsoft.Json` no aparece ahí, seleccione la pestaña **Examinar** y escriba "Newtonsoft.Json" en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6fc05-153">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="6fc05-154">Seleccione `Newtonsoft.Json` y, en el panel derecho, seleccione el proyecto antes de hacer clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-154">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="6fc05-155">Si `Newtonsoft.Json` ya está instalado en el sistema, agréguelo al proyecto seleccionando el proyecto en el panel derecho de la pestaña **Administrar paquetes para la solución**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-155">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="6fc05-156">Una implementación dependiente del marco con dependencias de terceros solo es tan portátil como sus dependencias de terceros.</span><span class="sxs-lookup"><span data-stu-id="6fc05-156">A framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="6fc05-157">Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se puede portar a sistemas Windows.</span><span class="sxs-lookup"><span data-stu-id="6fc05-157">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="6fc05-158">Esto ocurre si la dependencia de terceros propiamente dicha depende del código nativo.</span><span class="sxs-lookup"><span data-stu-id="6fc05-158">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="6fc05-159">Un buen ejemplo de esto es [el servidor Kestrel](/aspnet/core/fundamentals/servers/kestrel), que requiere una dependencia nativa de [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="6fc05-159">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="6fc05-160">Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contiene una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md) que admita la dependencia nativa (y que exista en su paquete de NuGet).</span><span class="sxs-lookup"><span data-stu-id="6fc05-160">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="self-contained-deployment-without-third-party-dependencies"></a><a name="simpleSelf"></a> <span data-ttu-id="6fc05-161">Implementación independiente sin dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="6fc05-161">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="6fc05-162">La implementación de una implementación independiente sin dependencias de terceros implica crear el proyecto, modificar el archivo *csproj* y compilar, probar y publicar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-162">Deploying a self-contained deployment with no third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="6fc05-163">Un sencillo ejemplo escrito en C# ilustra el proceso.</span><span class="sxs-lookup"><span data-stu-id="6fc05-163">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="6fc05-164">Empiece por crear, codificar y probar el proyecto, como haría en el caso de una implementación dependiente del marco de trabajo:</span><span class="sxs-lookup"><span data-stu-id="6fc05-164">You begin by creating, coding, and testing your project just as you would a framework-dependent deployment:</span></span>

1. <span data-ttu-id="6fc05-165">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fc05-165">Create the project.</span></span>

   <span data-ttu-id="6fc05-166">Seleccione **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-166">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="6fc05-167">En el cuadro de diálogo **Nuevo proyecto**, expanda las categorías de proyecto del lenguaje (C# o Visual Basic) en el panel de tipos de proyecto **instalados**, elija **.NET Core** y luego seleccione la plantilla **Aplicación de consola (.NET Core)** en el panel central.</span><span class="sxs-lookup"><span data-stu-id="6fc05-167">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="6fc05-168">Escriba un nombre de proyecto, como "SCD", en el cuadro de texto **Nombre** y pulse el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-168">Enter a project name, such as "SCD", in the **Name** text box, and select the **OK** button.</span></span>

1. <span data-ttu-id="6fc05-169">Agregar el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-169">Add the application's source code.</span></span>

   <span data-ttu-id="6fc05-170">Abra el archivo *Program.cs* o *Program.vb* en el editor y reemplace el código generado automáticamente por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fc05-170">Open the *Program.cs* or *Program.vb* file in your editor, and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="6fc05-171">Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6fc05-171">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="6fc05-172">Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="6fc05-172">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](./snippets/deploy-with-vs/csharp/deployment-example.cs)]
   [!code-vb[deployment#1](./snippets/deploy-with-vs/vb/deployment-example.vb)]

1. <span data-ttu-id="6fc05-173">Determine si quiere usar el modo de globalización invariable.</span><span class="sxs-lookup"><span data-stu-id="6fc05-173">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="6fc05-174">Especialmente si la aplicación es para Linux, puede reducir el tamaño total de la implementación si aprovecha las ventajas del [modo de globalización invariable](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6fc05-174">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span> <span data-ttu-id="6fc05-175">El modo de globalización invariable es útil para aquellas aplicaciones que no son globales y que pueden usar las convenciones de formato, las convenciones de mayúsculas y minúsculas y el criterio de ordenación y la comparación de cadenas de la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture).</span><span class="sxs-lookup"><span data-stu-id="6fc05-175">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="6fc05-176">Para habilitar el modo invariable, haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Editar SCD.csproj** o **Editar SCD.vbproj**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-176">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="6fc05-177">Luego agregue las siguientes líneas resaltadas al archivo:</span><span class="sxs-lookup"><span data-stu-id="6fc05-177">Then add the following highlighted lines to the file:</span></span>

   [!code-xml[globalization-invariant-mode](./snippets/deploy-with-vs/xml/invariant.csproj?highlight=7-9)]

1. <span data-ttu-id="6fc05-178">Cree una compilación de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-178">Create a Debug build of your application.</span></span>

   <span data-ttu-id="6fc05-179">Seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-179">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="6fc05-180">También puede compilar y ejecutar la versión de depuración de la aplicación seleccionando **Depurar** > **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-180">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span> <span data-ttu-id="6fc05-181">Este paso de depuración permite identificar problemas con la aplicación cuando se ejecuta en la plataforma de host.</span><span class="sxs-lookup"><span data-stu-id="6fc05-181">This debugging step lets you identify problems with your application when it's running on your host platform.</span></span> <span data-ttu-id="6fc05-182">Pero, aun así, tiene que probarla en cada una de las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-182">You still will have to test it on each of your target platforms.</span></span>

   <span data-ttu-id="6fc05-183">Si ha habilitado el modo de globalización invariable, asegúrese especialmente de probar si la ausencia de datos dependientes de la referencia cultural es adecuada para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-183">If you've enabled globalization invariant mode, be particularly sure to test whether the absence of culture-sensitive data is suitable for your application.</span></span>

<span data-ttu-id="6fc05-184">Una vez que haya terminado de depurar, puede publicar la implementación independiente:</span><span class="sxs-lookup"><span data-stu-id="6fc05-184">Once you've finished debugging, you can publish your self-contained deployment:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="6fc05-185">Visual Studio 15.6 y anterior</span><span class="sxs-lookup"><span data-stu-id="6fc05-185">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

<span data-ttu-id="6fc05-186">Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-186">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

<span data-ttu-id="6fc05-187">Para publicar la aplicación desde Visual Studio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6fc05-187">To publish your app from Visual Studio, do the following:</span></span>

1. <span data-ttu-id="6fc05-188">Definir las plataformas de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-188">Define the platforms that your app will target.</span></span>

   1. <span data-ttu-id="6fc05-189">Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Editar SCD.csproj**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-189">Right-click on your project (not the solution) in **Solution Explorer** and select **Edit SCD.csproj**.</span></span>

   1. <span data-ttu-id="6fc05-190">Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo *csproj* que defina las plataformas a las que se destina la aplicación y especifique el identificador en tiempo de ejecución (RID) de cada una.</span><span class="sxs-lookup"><span data-stu-id="6fc05-190">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets, and specify the runtime identifier (RID) of each platform that you target.</span></span> <span data-ttu-id="6fc05-191">También debe agregar un punto y coma para separar los RID.</span><span class="sxs-lookup"><span data-stu-id="6fc05-191">You also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="6fc05-192">Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="6fc05-192">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="6fc05-193">Por ejemplo, el ejemplo siguiente indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="6fc05-193">For example, the following example indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

   ```xml
   <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
   </PropertyGroup>
   ```

   <span data-ttu-id="6fc05-194">El elemento `<RuntimeIdentifiers>` puede ir en cualquier `<PropertyGroup>` que tenga en el archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="6fc05-194">The `<RuntimeIdentifiers>` element can go into any `<PropertyGroup>` that you have in your *csproj* file.</span></span> <span data-ttu-id="6fc05-195">Más adelante en esta sección aparece un ejemplo completo del archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="6fc05-195">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="6fc05-196">Publique la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-196">Publish your app.</span></span>

   <span data-ttu-id="6fc05-197">Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-197">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="6fc05-198">Para publicar la aplicación desde Visual Studio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6fc05-198">To publish your app from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="6fc05-199">Cambie la configuración de la solución de **Depurar** a **Versión** en la barra de herramientas para compilar una compilación de versión (en lugar de depuración) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-199">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="6fc05-200">Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-200">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="6fc05-201">En la pestaña **Publicar**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-201">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="6fc05-202">Visual Studio escribe los archivos que componen la aplicación en el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="6fc05-202">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="6fc05-203">La pestaña **Publicar** muestra ahora un solo perfil, **FolderProfile**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-203">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="6fc05-204">Los valores de configuración del perfil se muestran en la sección **Resumen** de la pestaña. **Tiempo de ejecución de destino** identifica qué tiempo de ejecución se ha publicado, y **Ubicación de destino** identifica dónde se escriben los archivos de la implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="6fc05-204">The profile's configuration settings are shown in the **Summary** section of the tab. **Target Runtime** identifies which runtime has been published, and **Target Location** identifies where the files for the self-contained deployment were written.</span></span>

      1. <span data-ttu-id="6fc05-205">De forma predeterminada, Visual Studio escribe todos los archivos publicados en un único directorio.</span><span class="sxs-lookup"><span data-stu-id="6fc05-205">Visual Studio by default writes all published files to a single directory.</span></span> <span data-ttu-id="6fc05-206">Para mayor comodidad, es mejor crear perfiles distintos para cada tiempo de ejecución de destino y colocar los archivos publicados en un directorio específico de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6fc05-206">For convenience, it's best to create separate profiles for each target runtime and to place published files in a platform-specific directory.</span></span> <span data-ttu-id="6fc05-207">Esto implica la creación de un perfil de publicación independiente para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-207">This involves creating a separate publishing profile for each target platform.</span></span> <span data-ttu-id="6fc05-208">Por tanto, vuelva a compilar la aplicación para cada plataforma siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6fc05-208">So now rebuild the application for each platform by doing the following:</span></span>

         1. <span data-ttu-id="6fc05-209">Seleccione **Crear nuevo perfil** en el cuadro de diálogo **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-209">Select **Create new profile** in the **Publish** dialog.</span></span>

         1. <span data-ttu-id="6fc05-210">En el cuadro de diálogo **Elegir un destino de publicación**, cambie la ubicación **Elegir una carpeta** a *bin\Release\PublishOutput\win10-x64*.</span><span class="sxs-lookup"><span data-stu-id="6fc05-210">In the **Pick a publish target** dialog, change the **Choose a folder** location to *bin\Release\PublishOutput\win10-x64*.</span></span> <span data-ttu-id="6fc05-211">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-211">Select **OK**.</span></span>

         1. <span data-ttu-id="6fc05-212">Seleccione el nuevo perfil (**FolderProfile1**) en la lista de perfiles y asegúrese de que el **Tiempo de ejecución de destino** es `win10-x64`.</span><span class="sxs-lookup"><span data-stu-id="6fc05-212">Select the new profile (**FolderProfile1**) in the list of profiles, and make sure that the **Target Runtime** is `win10-x64`.</span></span> <span data-ttu-id="6fc05-213">Si no lo es, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-213">If it isn't, select **Settings**.</span></span> <span data-ttu-id="6fc05-214">En el cuadro de diálogo **Configuración de perfil**, cambie **Tiempo de ejecución de destino** por `win10-x64` y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-214">In the **Profile Settings** dialog, change the **Target Runtime** to `win10-x64` and select **Save**.</span></span> <span data-ttu-id="6fc05-215">En caso contrario, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-215">Otherwise, select **Cancel**.</span></span>

         1. <span data-ttu-id="6fc05-216">Seleccione **Publicar** para publicar la aplicación para las plataformas de 64 bits de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6fc05-216">Select **Publish** to publish your app for 64-bit Windows 10 platforms.</span></span>

         1. <span data-ttu-id="6fc05-217">Siga los pasos anteriores de nuevo para crear un perfil para la plataforma `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="6fc05-217">Follow the previous steps again to create a profile for the `osx.10.11-x64` platform.</span></span> <span data-ttu-id="6fc05-218">La **Ubicación de destino** es *bin\Release\PublishOutput\osx.10.11-x64* y el **Tiempo de ejecución de destino** es `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="6fc05-218">The **Target Location** is *bin\Release\PublishOutput\osx.10.11-x64*, and the **Target Runtime** is `osx.10.11-x64`.</span></span> <span data-ttu-id="6fc05-219">El nombre que Visual Studio asigna a este perfil es **FolderProfile2**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-219">The name that Visual Studio assigns to this profile is **FolderProfile2**.</span></span>

      <span data-ttu-id="6fc05-220">Cada ubicación de destino contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesarios para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-220">Each target location contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="6fc05-221">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-221">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="6fc05-222">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="6fc05-222">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="6fc05-223">Puede decidir no empaquetarlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-223">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="6fc05-224">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-224">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="6fc05-225">Implemente los archivos publicados de la forma que quiera.</span><span class="sxs-lookup"><span data-stu-id="6fc05-225">Deploy the published files in any way you like.</span></span> <span data-ttu-id="6fc05-226">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6fc05-226">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="6fc05-227">A continuación se muestra el archivo *csproj* completo para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fc05-227">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="6fc05-228">Visual Studio 15.7 y posterior</span><span class="sxs-lookup"><span data-stu-id="6fc05-228">Visual Studio 15.7 and later</span></span>](#tab/vs157)

<span data-ttu-id="6fc05-229">Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-229">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span> <span data-ttu-id="6fc05-230">Esto implica la creación de un perfil independiente para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-230">This involves creating a separate profile for each target platform.</span></span>

<span data-ttu-id="6fc05-231">Haga lo siguiente para cada plataforma que sea destino de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6fc05-231">For each platform that your application targets, do the following:</span></span>

1. <span data-ttu-id="6fc05-232">Cree un perfil para la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-232">Create a profile for your target platform.</span></span>

   <span data-ttu-id="6fc05-233">Si este es el primer perfil que ha creado, haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-233">If this is the first profile you've created, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   <span data-ttu-id="6fc05-234">Si ya ha creado un perfil, haga clic con el botón derecho en el proyecto para abrir el cuadro de diálogo **Publicar**, si aún no está abierto.</span><span class="sxs-lookup"><span data-stu-id="6fc05-234">If you've already created a profile, right-click on the project to open the **Publish** dialog if it isn't already open.</span></span> <span data-ttu-id="6fc05-235">Luego seleccione **Nuevo perfil**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-235">Then select **New Profile**.</span></span>

   <span data-ttu-id="6fc05-236">Se abre el cuadro de diálogo **Elegir un destino de publicación**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-236">The **Pick a Publish Target** dialog box opens.</span></span>

1. <span data-ttu-id="6fc05-237">Seleccione la ubicación en la que Visual Studio publica la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-237">Select the location where Visual Studio publishes your application.</span></span>

   <span data-ttu-id="6fc05-238">Si solo se va a publicar en una plataforma, se puede aceptar el valor predeterminado del cuadro de texto **Elegir una carpeta**; así, se publica la implementación dependiente del marco de la aplicación en el directorio *\<project-directory>\bin\Release\netcoreapp2.1\publish*.</span><span class="sxs-lookup"><span data-stu-id="6fc05-238">If you're only publishing to a single platform, you can accept the default value in the **Choose a folder** text box; this publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish* directory.</span></span>

   <span data-ttu-id="6fc05-239">Si va a publicar en más de una plataforma, anexe una cadena que identifique a la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-239">If you're publishing to more than one platform, append a string that identifies the target platform.</span></span> <span data-ttu-id="6fc05-240">Por ejemplo, si anexa la cadena "linux" a la ruta de acceso de archivo, Visual Studio publica la implementación dependiente del marco de la aplicación en el directorio *\<project-directory>\bin\Release\netcoreapp2.1\publish\linux*.</span><span class="sxs-lookup"><span data-stu-id="6fc05-240">For example, if you append the string "linux" to the file path, Visual Studio publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish\linux* directory.</span></span>

1. <span data-ttu-id="6fc05-241">Para crear el perfil, seleccione el icono de lista desplegable situado junto al botón **Publicar** y luego **Crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-241">Create the profile by selecting the drop-down list icon next to the **Publish** button and selecting **Create Profile**.</span></span> <span data-ttu-id="6fc05-242">Después, seleccione el botón **Crear perfil** para crear el perfil.</span><span class="sxs-lookup"><span data-stu-id="6fc05-242">Then select the **Create Profile** button to create the profile.</span></span>

1. <span data-ttu-id="6fc05-243">Indique que va a publicar una implementación independiente y defina una plataforma como destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-243">Indicate that you are publishing a self-contained deployment and define a platform that your app will target.</span></span>

   1. <span data-ttu-id="6fc05-244">En el cuadro de diálogo **Publicar**, seleccione el vínculo **Configurar** para abrir el cuadro de diálogo **Configuración del perfil**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-244">In the **Publish** dialog, select the **Configure** link to open the **Profile Settings** dialog.</span></span>

   1. <span data-ttu-id="6fc05-245">Seleccione **Independiente** en el cuadro de lista **Modo de implementación**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-245">Select **Self-contained** in the **Deployment Mode** list box.</span></span>

   1. <span data-ttu-id="6fc05-246">En el cuadro de lista **Tiempo de ejecución de destino**, seleccione una de las plataformas de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-246">In the **Target Runtime** list box, select one of the platforms that your application targets.</span></span>

   1. <span data-ttu-id="6fc05-247">Seleccione **Guardar** para aceptar los cambios y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6fc05-247">Select **Save** to accept your changes and close the dialog.</span></span>

1. <span data-ttu-id="6fc05-248">Asigne un nombre al perfil.</span><span class="sxs-lookup"><span data-stu-id="6fc05-248">Name your profile.</span></span>

   1. <span data-ttu-id="6fc05-249">Seleccione **Acciones** > **Cambiar nombre de perfil** apara asignar el nombre al perfil.</span><span class="sxs-lookup"><span data-stu-id="6fc05-249">Select **Actions** > **Rename Profile** to name your profile.</span></span>

   2. <span data-ttu-id="6fc05-250">Asigne al perfil un nombre que identifique a la plataforma de destino y luego seleccione \**Guardar*.</span><span class="sxs-lookup"><span data-stu-id="6fc05-250">Assign your profile a name that identifies the target platform, then select \**Save*.</span></span>

<span data-ttu-id="6fc05-251">Repita estos pasos para definir las plataformas de destino adicionales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-251">Repeat these steps to define any additional target platforms that your application targets.</span></span>

<span data-ttu-id="6fc05-252">Ha configurado los perfiles y ahora está listo para publicar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-252">You've configured your profiles and are now ready to publish your app.</span></span> <span data-ttu-id="6fc05-253">Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="6fc05-253">To do this:</span></span>

   1. <span data-ttu-id="6fc05-254">Si la ventana **Publicar** no está abierta, haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-254">If the **Publish** window isn't currently open, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   2. <span data-ttu-id="6fc05-255">Seleccione el perfil que quiere publicar y luego **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-255">Select the profile that you'd like to publish, then select **Publish**.</span></span> <span data-ttu-id="6fc05-256">Realice este procedimiento para cada perfil que se vaya a publicar.</span><span class="sxs-lookup"><span data-stu-id="6fc05-256">Do this for each profile to be published.</span></span>

   <span data-ttu-id="6fc05-257">Cada ubicación de destino (en el caso de nuestro ejemplo, bin\release\netcoreapp2.1\publish\\*profile-name* contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesarios para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-257">Each target location (in the case of our example, bin\release\netcoreapp2.1\publish\\*profile-name* contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="6fc05-258">Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-258">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="6fc05-259">El archivo es útil principalmente para depurar excepciones.</span><span class="sxs-lookup"><span data-stu-id="6fc05-259">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="6fc05-260">Puede decidir no empaquetarlo con los archivos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-260">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="6fc05-261">Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-261">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="6fc05-262">Implemente los archivos publicados de la forma que quiera.</span><span class="sxs-lookup"><span data-stu-id="6fc05-262">Deploy the published files in any way you like.</span></span> <span data-ttu-id="6fc05-263">Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6fc05-263">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="6fc05-264">A continuación se muestra el archivo *csproj* completo para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fc05-264">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="6fc05-265">Además, Visual Studio crea un perfil de publicación independiente (\*.pubxml) para cada plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6fc05-265">In addition, Visual Studio creates a separate publishing profile (\*.pubxml) for each platform that you target.</span></span> <span data-ttu-id="6fc05-266">Por ejemplo, el archivo para nuestro perfil de Linux (linux.pubxml) aparece así:</span><span class="sxs-lookup"><span data-stu-id="6fc05-266">For example, the file for our linux profile (linux.pubxml) appears as follows:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
https://go.microsoft.com/fwlink/?LinkID=208121.
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PublishProtocol>FileSystem</PublishProtocol>
    <Configuration>Release</Configuration>
    <Platform>Any CPU</Platform>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <PublishDir>bin\Release\netcoreapp2.1\publish\linux</PublishDir>
    <RuntimeIdentifier>win-x86</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <_IsPortable>false</_IsPortable>
  </PropertyGroup>
</Project>
```

---

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="6fc05-267">Implementación autocontenida con dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="6fc05-267">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="6fc05-268">Implementar una implementación independiente con una o varias dependencias de terceros implica agregar las dependencias.</span><span class="sxs-lookup"><span data-stu-id="6fc05-268">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="6fc05-269">Se requieren los pasos adicionales siguientes antes de poder compilar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6fc05-269">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="6fc05-270">Use el **Administrador de paquetes NuGet** para agregar una referencia a un paquete de NuGet para el proyecto y, si el paquete todavía no está disponible en el sistema, instálelo.</span><span class="sxs-lookup"><span data-stu-id="6fc05-270">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="6fc05-271">Para abrir el administrador de paquetes, seleccione **Herramientas** > **Administrador de paquetes NuGet** > **Administrar paquetes NuGet para la solución**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-271">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="6fc05-272">Confirme que las dependencias de terceros (por ejemplo, `Newtonsoft.Json`) están instaladas en el sistema y, si no es así, instálelas.</span><span class="sxs-lookup"><span data-stu-id="6fc05-272">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="6fc05-273">La pestaña **Instalado** enumera los paquetes de NuGet instalados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="6fc05-273">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="6fc05-274">Si `Newtonsoft.Json` no aparece ahí, seleccione la pestaña **Examinar** y escriba "Newtonsoft.Json" en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6fc05-274">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="6fc05-275">Seleccione `Newtonsoft.Json` y, en el panel derecho, seleccione el proyecto antes de hacer clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-275">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="6fc05-276">Si `Newtonsoft.Json` ya está instalado en el sistema, agréguelo al proyecto seleccionando el proyecto en el panel derecho de la pestaña **Administrar paquetes para la solución**.</span><span class="sxs-lookup"><span data-stu-id="6fc05-276">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="6fc05-277">A continuación se muestra el archivo *csproj* completo de este proyecto:</span><span class="sxs-lookup"><span data-stu-id="6fc05-277">The following is the complete *csproj* file for this project:</span></span>

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="6fc05-278">Visual Studio 15.6 y anterior</span><span class="sxs-lookup"><span data-stu-id="6fc05-278">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

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

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="6fc05-279">Visual Studio 15.7 y posterior</span><span class="sxs-lookup"><span data-stu-id="6fc05-279">Visual Studio 15.7 and later</span></span>](#tab/vs157)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

---

<span data-ttu-id="6fc05-280">Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-280">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="6fc05-281">No se requieren las bibliotecas de terceros en el sistema en el que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6fc05-281">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="6fc05-282">Solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6fc05-282">You can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="6fc05-283">Esto es similar a tener dependencias de terceros con dependencias nativas en la implementación dependiente de la plataforma, donde las dependencias nativas no existirán en la plataforma de destino a menos que se hayan instalado allí previamente.</span><span class="sxs-lookup"><span data-stu-id="6fc05-283">This is similar to having third-party dependencies with native dependencies in your framework-dependent deployment, where the native dependencies won't exist on the target platform unless they were previously installed there.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fc05-284">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fc05-284">See also</span></span>

- [<span data-ttu-id="6fc05-285">Implementación de aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="6fc05-285">.NET Core Application Deployment</span></span>](index.md)
- [<span data-ttu-id="6fc05-286">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6fc05-286">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

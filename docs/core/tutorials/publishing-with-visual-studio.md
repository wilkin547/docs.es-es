---
title: Publicación de la aplicación Hola mundo de .NET Core con Visual Studio
description: La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación de .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 485d62ce67f284fe1bbe931dcaa00671be154f35
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715367"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a><span data-ttu-id="e4c79-103">Publicación de la aplicación Hola mundo de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e4c79-103">Publish your .NET Core Hello World application with Visual Studio</span></span>

<span data-ttu-id="e4c79-104">En [Creación de una aplicación Hola mundo con .NET Core en Visual Studio](with-visual-studio.md), ha compilado una aplicación de consola Hola mundo.</span><span class="sxs-lookup"><span data-stu-id="e4c79-104">In [Create a Hello World application with .NET Core in Visual Studio](with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="e4c79-105">En [Depuración de la aplicación Hola mundo con Visual Studio](debugging-with-visual-studio.md), la ha probado con el depurador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4c79-105">In [Debug your Hello World application with Visual Studio](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="e4c79-106">Ahora que está seguro de que funciona como se esperaba, puede publicarla para que otros usuarios puedan ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="e4c79-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="e4c79-107">La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-107">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="e4c79-108">Para implementar los archivos, cópielos en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="e4c79-108">To deploy the files, copy them to the target machine.</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="e4c79-109">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="e4c79-109">Publish the app</span></span>

1. <span data-ttu-id="e4c79-110">Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="e4c79-111">Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="e4c79-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Barra de herramientas de Visual Studio con compilación de versión seleccionado](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="e4c79-113">Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="e4c79-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="e4c79-114">(también puede seleccionar **Publicar Hola mundo** en el menú principal **Compilar**).</span><span class="sxs-lookup"><span data-stu-id="e4c79-114">(You can also select **Publish HelloWorld** from the main **Build** menu.)</span></span>

   ![Menú contextual de Publicar de Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)
   
1. <span data-ttu-id="e4c79-116">En la página **Elegir un destino de publicación**, seleccione **Carpeta** y, a continuación, seleccione **Crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="e4c79-116">On the **Pick a publish target** page, select **Folder**, and then select **Create Profile**.</span></span>

   ![Elegir un destino de publicación en Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)
   
1. <span data-ttu-id="e4c79-118">En la página **Publicar**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e4c79-118">On the **Publish** page, select **Publish**.</span></span>

   ![Ventana Publicar de Visual Studio](media/publishing-with-visual-studio/publish-page.png)
   
## <a name="inspect-the-files"></a><span data-ttu-id="e4c79-120">Inspección de los archivos</span><span class="sxs-lookup"><span data-stu-id="e4c79-120">Inspect the files</span></span>

<span data-ttu-id="e4c79-121">El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en cualquier plataforma compatible con .NET Core con .NET Core instalado en el sistema.</span><span class="sxs-lookup"><span data-stu-id="e4c79-121">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="e4c79-122">Los usuarios pueden ejecutar la aplicación publicada haciendo doble clic en el archivo ejecutable o emitiendo el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4c79-122">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="e4c79-123">En los pasos siguientes, examinará los archivos creados por el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-123">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="e4c79-124">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4c79-124">Open a command prompt.</span></span>

   <span data-ttu-id="e4c79-125">Una forma de abrir un símbolo del sistema es escribir **Símbolo del sistema** (o **cmd**) en el cuadro de búsqueda de la barra de tareas de Windows.</span><span class="sxs-lookup"><span data-stu-id="e4c79-125">One way to open a command prompt is to enter **Command Prompt** (or **cmd** for short) in the search box on the Windows taskbar.</span></span> <span data-ttu-id="e4c79-126">Seleccione la aplicación de escritorio **Símbolo del sistema** o presione **Entrar** si ya está seleccionado en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e4c79-126">Select the **Command Prompt** desktop app, or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="e4c79-127">Vaya a la aplicación publicada en el subdirectorio *bin\Release\netcoreapp3.1\publish* del directorio del proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-127">Navigate to the published application in the *bin\Release\netcoreapp3.1\publish* subdirectory of the application's project directory.</span></span>

   ![Ventana de la consola que muestra los archivos publicados](media/publishing-with-visual-studio/published-files-output.png)

   <span data-ttu-id="e4c79-129">Como se muestra en la imagen, el resultado publicado incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="e4c79-129">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="e4c79-130">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="e4c79-130">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="e4c79-131">Este es el archivo de dependencias en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-131">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="e4c79-132">Define los componentes y las bibliotecas de .NET Core (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-132">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="e4c79-133">Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="e4c79-133">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="e4c79-134">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="e4c79-134">*HelloWorld.dll*</span></span>

         <span data-ttu-id="e4c79-135">Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-135">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="e4c79-136">Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4c79-136">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="e4c79-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="e4c79-137">*HelloWorld.exe*</span></span>
      
         <span data-ttu-id="e4c79-138">Esta es la versión del [ejecutable dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-executable) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="e4c79-139">Para ejecutarlo, escriba `HelloWorld.exe` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4c79-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="e4c79-140">*HelloWorld.pdb* (opcional para la implementación)</span><span class="sxs-lookup"><span data-stu-id="e4c79-140">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="e4c79-141">Este es el archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="e4c79-141">This is the debug symbols file.</span></span> <span data-ttu-id="e4c79-142">No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-142">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="e4c79-143">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="e4c79-143">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="e4c79-144">Este es el archivo de configuración en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e4c79-144">This is the application's runtime configuration file.</span></span> <span data-ttu-id="e4c79-145">Identifica la versión de .NET Core en la que se ha compilado la aplicación para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e4c79-145">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="e4c79-146">Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="e4c79-146">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4c79-147">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e4c79-147">Additional resources</span></span>

- [<span data-ttu-id="e4c79-148">Implementación de aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="e4c79-148">.NET Core application deployment</span></span>](../deploying/index.md)

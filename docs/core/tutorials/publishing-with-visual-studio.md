---
title: Publicación de la aplicación Hola mundo de .NET Core con Visual Studio
description: La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación de .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e4ef8c12f3e52faa7cf09058a98abae65b0dcfce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005126"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="93ad3-103">Tutorial: Publicación de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93ad3-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="93ad3-104">En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="93ad3-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="93ad3-105">La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="93ad3-106">Para implementar los archivos, cópielos en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="93ad3-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="93ad3-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="93ad3-107">Prerequisites</span></span>

- <span data-ttu-id="93ad3-108">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET Core en Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="93ad3-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="93ad3-109">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="93ad3-109">Publish the app</span></span>

1. <span data-ttu-id="93ad3-110">Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="93ad3-111">Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="93ad3-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Barra de herramientas de Visual Studio con compilación de versión seleccionado](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="93ad3-113">Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="93ad3-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Menú contextual de Publicar de Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="93ad3-115">En la pestaña **Destino** de la página **Publicar**, seleccione **Carpeta** y luego **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93ad3-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Elegir un destino de publicación en Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="93ad3-117">En la pestaña **Ubicación** de la página **Publicar**, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="93ad3-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Pestaña Ubicación de la página Publicar de Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="93ad3-119">En la pestaña **Publicar** de la ventana **Publicar**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="93ad3-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Ventana Publicar de Visual Studio](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="93ad3-121">Inspección de los archivos</span><span class="sxs-lookup"><span data-stu-id="93ad3-121">Inspect the files</span></span>

<span data-ttu-id="93ad3-122">El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en cualquier máquina que tenga instalado .NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="93ad3-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="93ad3-123">Los usuarios pueden ejecutar la aplicación publicada haciendo doble clic en el archivo ejecutable o emitiendo el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="93ad3-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="93ad3-124">En los pasos siguientes, examinará los archivos creados por el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="93ad3-125">En el **Explorador de soluciones**, elija **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="93ad3-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="93ad3-126">En la carpeta del proyecto, expanda *bin/Release/netcoreapp3.1/publish*.</span><span class="sxs-lookup"><span data-stu-id="93ad3-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Explorador de soluciones donde se muestran los archivos publicados":::

   <span data-ttu-id="93ad3-128">Como se muestra en la imagen, el resultado publicado incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="93ad3-128">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="93ad3-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="93ad3-129">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="93ad3-130">Este es el archivo de dependencias en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="93ad3-131">Define los componentes y las bibliotecas de .NET Core (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="93ad3-132">Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="93ad3-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="93ad3-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="93ad3-133">*HelloWorld.dll*</span></span>

         <span data-ttu-id="93ad3-134">Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="93ad3-135">Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="93ad3-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="93ad3-136">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="93ad3-136">*HelloWorld.exe*</span></span>

         <span data-ttu-id="93ad3-137">Esta es la versión del [ejecutable dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-executable) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-137">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="93ad3-138">Para ejecutarlo, escriba `HelloWorld.exe` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="93ad3-138">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="93ad3-139">*HelloWorld.pdb* (opcional para la implementación)</span><span class="sxs-lookup"><span data-stu-id="93ad3-139">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="93ad3-140">Este es el archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="93ad3-140">This is the debug symbols file.</span></span> <span data-ttu-id="93ad3-141">No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-141">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="93ad3-142">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="93ad3-142">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="93ad3-143">Este es el archivo de configuración en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ad3-143">This is the application's run-time configuration file.</span></span> <span data-ttu-id="93ad3-144">Identifica la versión de .NET Core en la que se ha compilado la aplicación para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="93ad3-144">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="93ad3-145">También puede agregarle opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="93ad3-145">You can also add configuration options to it.</span></span> <span data-ttu-id="93ad3-146">Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="93ad3-146">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="93ad3-147">Ejecutar la aplicación publicada</span><span class="sxs-lookup"><span data-stu-id="93ad3-147">Run the published app</span></span>

1. <span data-ttu-id="93ad3-148">En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta *Publicar* y seleccione **Copiar ruta de acceso completa**.</span><span class="sxs-lookup"><span data-stu-id="93ad3-148">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="93ad3-149">Abra un símbolo del sistema y vaya a la carpeta *Publicar*.</span><span class="sxs-lookup"><span data-stu-id="93ad3-149">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="93ad3-150">Escriba `cd` y pegue la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="93ad3-150">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="93ad3-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="93ad3-151">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="93ad3-152">Ejecute la aplicación con el archivo ejecutable:</span><span class="sxs-lookup"><span data-stu-id="93ad3-152">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="93ad3-153">Escriba `HelloWorld.exe` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="93ad3-153">Enter `HelloWorld.exe` and press Enter.</span></span>

   1. <span data-ttu-id="93ad3-154">Escriba un nombre cuando se le pida y presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="93ad3-154">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="93ad3-155">Ejecute la aplicación mediante el comando `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="93ad3-155">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="93ad3-156">Escriba `dotnet HelloWorld.dll` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="93ad3-156">Enter `dotnet HelloWorld.dll` and press Enter.</span></span>

   1. <span data-ttu-id="93ad3-157">Escriba un nombre cuando se le pida y presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="93ad3-157">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93ad3-158">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="93ad3-158">Additional resources</span></span>

- [<span data-ttu-id="93ad3-159">Implementación de aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="93ad3-159">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="93ad3-160">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="93ad3-160">Next steps</span></span>

<span data-ttu-id="93ad3-161">En este tutorial, ha publicado una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="93ad3-161">In this tutorial, you published a console app.</span></span> <span data-ttu-id="93ad3-162">En el siguiente tutorial, creará una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="93ad3-162">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="93ad3-163">Creación de una biblioteca de .NET Standard en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93ad3-163">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)

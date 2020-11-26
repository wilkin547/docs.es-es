---
title: Publicación de una aplicación de consola de .NET con Visual Studio
description: Obtenga información sobre cómo usar Visual Studio para crear el conjunto de archivos necesarios para ejecutar una aplicación de .NET.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: b0c6bd85ddf86f0eb11c56f01abb74a7e9786363
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916034"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio"></a><span data-ttu-id="d3821-103">Tutorial: Publicación de una aplicación de consola de .NET con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d3821-103">Tutorial: Publish a .NET console application using Visual Studio</span></span>

<span data-ttu-id="d3821-104">En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="d3821-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="d3821-105">La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="d3821-106">Para implementar los archivos, cópielos en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d3821-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3821-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d3821-107">Prerequisites</span></span>

- <span data-ttu-id="d3821-108">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d3821-108">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="d3821-109">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="d3821-109">Publish the app</span></span>

1. <span data-ttu-id="d3821-110">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3821-110">Start Visual Studio.</span></span>

1. <span data-ttu-id="d3821-111">Abra el proyecto *HelloWorld* que ha creado en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d3821-111">Open the *HelloWorld* project that you created in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

1. <span data-ttu-id="d3821-112">Asegúrese de que Visual Studio usa la configuración de compilación de versión.</span><span class="sxs-lookup"><span data-stu-id="d3821-112">Make sure that Visual Studio is using the Release build configuration.</span></span> <span data-ttu-id="d3821-113">Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="d3821-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Barra de herramientas de Visual Studio con compilación de versión seleccionada":::

1. <span data-ttu-id="d3821-115">Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="d3821-115">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-context-menu.png" alt-text="Menú contextual Publicar de Visual Studio":::

1. <span data-ttu-id="d3821-117">En la pestaña **Destino** de la página **Publicar**, seleccione **Carpeta** y luego **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3821-117">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-publish-target.png" alt-text="Elegir un destino de publicación en Visual Studio":::

1. <span data-ttu-id="d3821-119">En la pestaña **Destino específico** de la página **Publicar**, seleccione **Carpeta** y luego **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3821-119">On the **Specific Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/pick-specific-publish-target.png" alt-text="Elección del destino de publicación específico en Visual Studio":::

1. <span data-ttu-id="d3821-121">En la pestaña **Ubicación** de la página **Publicar**, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d3821-121">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page-loc-tab.png" alt-text="Pestaña Ubicación de la página Publicar de Visual Studio":::

1. <span data-ttu-id="d3821-123">En la pestaña **Publicar** de la ventana **Publicar**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d3821-123">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/publish-page.png" alt-text="Ventana Publicar de Visual Studio":::

## <a name="inspect-the-files"></a><span data-ttu-id="d3821-125">Inspección de los archivos</span><span class="sxs-lookup"><span data-stu-id="d3821-125">Inspect the files</span></span>

<span data-ttu-id="d3821-126">De forma predeterminada, el proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en un equipo con el entorno de ejecución de .NET instalado.</span><span class="sxs-lookup"><span data-stu-id="d3821-126">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET runtime installed.</span></span> <span data-ttu-id="d3821-127">Los usuarios pueden ejecutar la aplicación publicada haciendo doble clic en el archivo ejecutable o emitiendo el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d3821-127">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="d3821-128">En los pasos siguientes, examinará los archivos creados por el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-128">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="d3821-129">En el **Explorador de soluciones**, elija **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="d3821-129">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="d3821-130">En la carpeta del proyecto, expanda *bin/Release/net5.0/publish*.</span><span class="sxs-lookup"><span data-stu-id="d3821-130">In the project folder, expand *bin/Release/net5.0/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Explorador de soluciones donde se muestran los archivos publicados":::

   <span data-ttu-id="d3821-132">Como se muestra en la imagen, el resultado publicado incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="d3821-132">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="d3821-133">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="d3821-133">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="d3821-134">Este es el archivo de dependencias en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-134">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="d3821-135">Define los componentes y las bibliotecas de .NET (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-135">It defines the .NET components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="d3821-136">Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="d3821-136">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="d3821-137">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="d3821-137">*HelloWorld.dll*</span></span>

      <span data-ttu-id="d3821-138">Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-138">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="d3821-139">Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d3821-139">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="d3821-140">Este método de ejecución de la aplicación funciona en cualquier plataforma que tenga instalado el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="d3821-140">This method of running the app works on any platform that has the .NET runtime installed.</span></span>

   * <span data-ttu-id="d3821-141">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="d3821-141">*HelloWorld.exe*</span></span>

      <span data-ttu-id="d3821-142">Esta es la versión del [ejecutable dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-executable) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-142">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="d3821-143">Para ejecutarlo, escriba `HelloWorld.exe` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="d3821-143">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="d3821-144">El archivo es específico del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d3821-144">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="d3821-145">*HelloWorld.pdb* (opcional para la implementación)</span><span class="sxs-lookup"><span data-stu-id="d3821-145">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="d3821-146">Este es el archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="d3821-146">This is the debug symbols file.</span></span> <span data-ttu-id="d3821-147">No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-147">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="d3821-148">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="d3821-148">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="d3821-149">Este es el archivo de configuración en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3821-149">This is the application's run-time configuration file.</span></span> <span data-ttu-id="d3821-150">Identifica la versión de .NET en la que se ha compilado la aplicación para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d3821-150">It identifies the version of .NET that your application was built to run on.</span></span> <span data-ttu-id="d3821-151">También puede agregarle opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="d3821-151">You can also add configuration options to it.</span></span> <span data-ttu-id="d3821-152">Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="d3821-152">For more information, see [.NET run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="d3821-153">Ejecutar la aplicación publicada</span><span class="sxs-lookup"><span data-stu-id="d3821-153">Run the published app</span></span>

1. <span data-ttu-id="d3821-154">En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta *Publicar* y seleccione **Copiar ruta de acceso completa**.</span><span class="sxs-lookup"><span data-stu-id="d3821-154">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="d3821-155">Abra un símbolo del sistema y vaya a la carpeta *Publicar*.</span><span class="sxs-lookup"><span data-stu-id="d3821-155">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="d3821-156">Para ello, escriba `cd` y pegue la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="d3821-156">To do that, enter `cd` and then paste the full path.</span></span> <span data-ttu-id="d3821-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d3821-157">For example:</span></span>

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="d3821-158">Ejecute la aplicación con el archivo ejecutable:</span><span class="sxs-lookup"><span data-stu-id="d3821-158">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="d3821-159">Escriba `HelloWorld.exe` y presione <kbd>ENTRAR</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d3821-159">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="d3821-160">Escriba un nombre cuando se le pida y presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="d3821-160">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="d3821-161">Ejecute la aplicación mediante el comando `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="d3821-161">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="d3821-162">Escriba `dotnet HelloWorld.dll` y presione <kbd>ENTRAR</kbd>.</span><span class="sxs-lookup"><span data-stu-id="d3821-162">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="d3821-163">Escriba un nombre cuando se le pida y presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="d3821-163">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d3821-164">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d3821-164">Additional resources</span></span>

- [<span data-ttu-id="d3821-165">implementación de aplicaciones .NET</span><span class="sxs-lookup"><span data-stu-id="d3821-165">.NET application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="d3821-166">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d3821-166">Next steps</span></span>

<span data-ttu-id="d3821-167">En este tutorial, ha publicado una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="d3821-167">In this tutorial, you published a console app.</span></span> <span data-ttu-id="d3821-168">En el siguiente tutorial, creará una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="d3821-168">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3821-169">Creación de una biblioteca de clases de .NET con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d3821-169">Create a .NET class library using Visual Studio</span></span>](library-with-visual-studio.md)

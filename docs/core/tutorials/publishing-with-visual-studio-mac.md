---
title: Publicación de una aplicación de consola de .NET con Visual Studio para Mac
description: Aprenda a usar Visual Studio para Mac para crear el conjunto de archivos necesarios para ejecutar una aplicación de .NET.
ms.date: 11/30/2020
ms.openlocfilehash: 88f143011b19ca8eda6610803c894e619d06a635
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599196"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="f728f-103">Tutorial: Publicación de una aplicación de consola de .NET con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="f728f-103">Tutorial: Publish a .NET console application using Visual Studio for Mac</span></span>

<span data-ttu-id="f728f-104">En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="f728f-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="f728f-105">La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f728f-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="f728f-106">Para implementar los archivos, cópielos en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="f728f-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f728f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f728f-107">Prerequisites</span></span>

- <span data-ttu-id="f728f-108">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio para Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="f728f-108">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="f728f-109">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f728f-109">Publish the app</span></span>

1. <span data-ttu-id="f728f-110">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="f728f-110">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="f728f-111">Abra el proyecto HelloWorld que creó en [Creación de una aplicación de consola de .NET con Visual Studio para Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="f728f-111">Open the HelloWorld project that you created in [Create a .NET console application using Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

1. <span data-ttu-id="f728f-112">Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f728f-112">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="f728f-113">Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="f728f-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="Barra de herramientas de Visual Studio con compilación de versión seleccionada":::

1. <span data-ttu-id="f728f-115">En el menú principal, elija **Compilación** > **Publicar en carpeta...** .</span><span class="sxs-lookup"><span data-stu-id="f728f-115">From the main menu, choose **Build** > **Publish to Folder...**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Menú contextual Publicar de Visual Studio":::

1. <span data-ttu-id="f728f-117">En el cuadro de diálogo **Publicar en carpeta**, seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f728f-117">In the **Publish to Folder** dialog, select **Publish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Cuadro de diálogo Publicar en carpeta de Visual Studio":::

   <span data-ttu-id="f728f-119">Se abre la carpeta de publicación, que muestra los archivos que se crearon.</span><span class="sxs-lookup"><span data-stu-id="f728f-119">The publish folder opens, showing the files that were created.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="carpeta de publicación":::

1. <span data-ttu-id="f728f-121">Seleccione el icono de engranaje y elija **Copy "publish" as Pathname** (Copiar "publicar" como nombre de ruta) en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="f728f-121">Select the gear icon, and select **Copy "publish" as Pathname** from the context menu.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="Copiar ruta de acceso en la carpeta de publicación":::

## <a name="inspect-the-files"></a><span data-ttu-id="f728f-123">Inspección de los archivos</span><span class="sxs-lookup"><span data-stu-id="f728f-123">Inspect the files</span></span>

<span data-ttu-id="f728f-124">El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en cualquier máquina que tenga instalado el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="f728f-124">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET runtime installed.</span></span> <span data-ttu-id="f728f-125">Los usuarios pueden ejecutar la aplicación publicada mediante la ejecución del comando `dotnet HelloWorld.dll` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f728f-125">Users can run the published app by running the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="f728f-126">Como se muestra en la imagen anterior, la salida publicada incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="f728f-126">As the preceding image shows, the published output includes the following files:</span></span>

* <span data-ttu-id="f728f-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="f728f-127">*HelloWorld.deps.json*</span></span>

  <span data-ttu-id="f728f-128">Este es el archivo de dependencias en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f728f-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="f728f-129">Define los componentes y las bibliotecas de .NET (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f728f-129">It defines the .NET components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="f728f-130">Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="f728f-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

* <span data-ttu-id="f728f-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="f728f-131">*HelloWorld.dll*</span></span>

   <span data-ttu-id="f728f-132">Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f728f-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="f728f-133">Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f728f-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="f728f-134">Este método de ejecución de la aplicación funciona en cualquier plataforma que tenga instalado el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="f728f-134">This method of running the app works on any platform that has the .NET runtime installed.</span></span>

* <span data-ttu-id="f728f-135">*HelloWorld.pdb* (opcional para la implementación)</span><span class="sxs-lookup"><span data-stu-id="f728f-135">*HelloWorld.pdb* (optional for deployment)</span></span>

   <span data-ttu-id="f728f-136">Este es el archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="f728f-136">This is the debug symbols file.</span></span> <span data-ttu-id="f728f-137">No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f728f-137">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

* <span data-ttu-id="f728f-138">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="f728f-138">*HelloWorld.runtimeconfig.json*</span></span>

   <span data-ttu-id="f728f-139">Este es el archivo de configuración en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f728f-139">This is the application's run-time configuration file.</span></span> <span data-ttu-id="f728f-140">Identifica la versión de .NET en la que se ha compilado la aplicación para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="f728f-140">It identifies the version of .NET that your application was built to run on.</span></span> <span data-ttu-id="f728f-141">También puede agregarle opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="f728f-141">You can also add configuration options to it.</span></span> <span data-ttu-id="f728f-142">Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="f728f-142">For more information, see [.NET run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="f728f-143">Ejecutar la aplicación publicada</span><span class="sxs-lookup"><span data-stu-id="f728f-143">Run the published app</span></span>

1. <span data-ttu-id="f728f-144">Abra un terminal y vaya a la carpeta *publish*.</span><span class="sxs-lookup"><span data-stu-id="f728f-144">Open a terminal and navigate to the *publish* folder.</span></span> <span data-ttu-id="f728f-145">Para ello, escriba `cd` y, luego, pegue la ruta de acceso que copió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f728f-145">To do that, enter `cd` and then paste the path that you copied earlier.</span></span> <span data-ttu-id="f728f-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f728f-146">For example:</span></span>

   ```console
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/net5.0/publish/
   ```

1. <span data-ttu-id="f728f-147">Ejecute la aplicación mediante el comando `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="f728f-147">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="f728f-148">Escriba `dotnet HelloWorld.dll` y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="f728f-148">Enter `dotnet HelloWorld.dll` and press <kbd>enter</kbd>.</span></span>

   1. <span data-ttu-id="f728f-149">Escriba un nombre cuando se le pida y presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="f728f-149">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f728f-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f728f-150">Additional resources</span></span>

- [<span data-ttu-id="f728f-151">implementación de aplicaciones .NET</span><span class="sxs-lookup"><span data-stu-id="f728f-151">.NET application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="f728f-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f728f-152">Next steps</span></span>

<span data-ttu-id="f728f-153">En este tutorial, ha publicado una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="f728f-153">In this tutorial, you published a console app.</span></span> <span data-ttu-id="f728f-154">En el siguiente tutorial, creará una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="f728f-154">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f728f-155">Creación de una biblioteca .NET mediante Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="f728f-155">Create a .NET library using Visual Studio for Mac</span></span>](library-with-visual-studio-mac.md)

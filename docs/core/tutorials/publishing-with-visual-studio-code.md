---
title: Publicación de una aplicación de consola de .NET con Visual Studio Code
description: Obtenga información sobre cómo usar Visual Studio Code y la CLI de .NET para crear el conjunto de archivos necesarios para ejecutar una aplicación de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 9cfe490203d2d3254103ad2f0a4c4ff74972ec64
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94915894"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="4f324-103">Tutorial: Publicación de una aplicación de consola de .NET con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4f324-103">Tutorial: Publish a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="4f324-104">En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="4f324-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="4f324-105">La publicación crea el conjunto de archivos que se necesitan para ejecutar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-105">Publishing creates the set of files that are needed to run an application.</span></span> <span data-ttu-id="4f324-106">Para implementar los archivos, cópielos en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="4f324-106">To deploy the files, copy them to the target machine.</span></span>

<span data-ttu-id="4f324-107">La CLI de .NET se usa para publicar la aplicación, por lo que puede seguir este tutorial con un editor de código que no sea Visual Studio Code si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="4f324-107">The .NET CLI is used to publish the app, so you can follow this tutorial with a code editor other than Visual Studio Code if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4f324-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4f324-108">Prerequisites</span></span>

- <span data-ttu-id="4f324-109">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="4f324-109">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="4f324-110">Publicar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4f324-110">Publish the app</span></span>

1. <span data-ttu-id="4f324-111">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4f324-111">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="4f324-112">Abra la carpeta de proyecto *HelloWorld* que ha creado en [Creación de una aplicación de consola de .NET con Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="4f324-112">Open the *HelloWorld* project folder that you created in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="4f324-113">Elija **Ver** > **Terminal** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="4f324-113">Choose **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="4f324-114">Se abrirá el terminal en la carpeta *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="4f324-114">The terminal opens in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="4f324-115">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4f324-115">Run the following command:</span></span>

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   <span data-ttu-id="4f324-116">La configuración de compilación predeterminada es *Depuración*, por lo que este comando especifica la versión de la configuración de compilación *Versión*.</span><span class="sxs-lookup"><span data-stu-id="4f324-116">The default build configuration is *Debug*, so this command specifies the *Release* build configuration.</span></span> <span data-ttu-id="4f324-117">La salida de la configuración de compilación Versión tiene muy poca información de depuración simbólica y está totalmente optimizada.</span><span class="sxs-lookup"><span data-stu-id="4f324-117">The output from the Release build configuration has minimal symbolic debug information and is fully optimized.</span></span>

   <span data-ttu-id="4f324-118">La salida del comando es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f324-118">The command output is similar to the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
     HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a><span data-ttu-id="4f324-119">Inspección de los archivos</span><span class="sxs-lookup"><span data-stu-id="4f324-119">Inspect the files</span></span>

<span data-ttu-id="4f324-120">De forma predeterminada, el proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en un equipo que tenga instalado el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="4f324-120">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET runtime installed.</span></span> <span data-ttu-id="4f324-121">Para ejecutar la aplicación publicada, puede usar el archivo ejecutable o ejecutar el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4f324-121">To run the published app you can use the executable file or run the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="4f324-122">En los pasos siguientes, examinará los archivos creados por el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-122">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="4f324-123">Seleccione **Explorador** en la barra de navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="4f324-123">Select the **Explorer** in the left navigation bar.</span></span>

1. <span data-ttu-id="4f324-124">Expanda *bin/Release/net5.0/publish*.</span><span class="sxs-lookup"><span data-stu-id="4f324-124">Expand *bin/Release/net5.0/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="Explorador donde se muestran los archivos publicados":::

   <span data-ttu-id="4f324-126">Como se muestra en la imagen, el resultado publicado incluye los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="4f324-126">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="4f324-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="4f324-127">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="4f324-128">Este es el archivo de dependencias en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="4f324-129">Define los componentes y las bibliotecas de .NET (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-129">It defines the .NET components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="4f324-130">Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="4f324-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="4f324-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="4f324-131">*HelloWorld.dll*</span></span>

      <span data-ttu-id="4f324-132">Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="4f324-133">Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4f324-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="4f324-134">Este método de ejecución de la aplicación funciona en cualquier plataforma que tenga instalado el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="4f324-134">This method of running the app works on any platform that has the .NET runtime installed.</span></span>

   * <span data-ttu-id="4f324-135">*HelloWorld.exe* (*HelloWorld* en Linux, no creada en macOS).</span><span class="sxs-lookup"><span data-stu-id="4f324-135">*HelloWorld.exe* (*HelloWorld* on Linux, not created on macOS.)</span></span>

      <span data-ttu-id="4f324-136">Esta es la versión del [ejecutable dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-executable) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-136">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="4f324-137">El archivo es específico del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4f324-137">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="4f324-138">*HelloWorld.pdb* (opcional para la implementación)</span><span class="sxs-lookup"><span data-stu-id="4f324-138">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="4f324-139">Este es el archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="4f324-139">This is the debug symbols file.</span></span> <span data-ttu-id="4f324-140">No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-140">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="4f324-141">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="4f324-141">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="4f324-142">Este es el archivo de configuración en tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4f324-142">This is the application's run-time configuration file.</span></span> <span data-ttu-id="4f324-143">Identifica la versión de .NET en la que se ha compilado la aplicación para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="4f324-143">It identifies the version of .NET that your application was built to run on.</span></span> <span data-ttu-id="4f324-144">También puede agregarle opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="4f324-144">You can also add configuration options to it.</span></span> <span data-ttu-id="4f324-145">Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="4f324-145">For more information, see [.NET run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="4f324-146">Ejecutar la aplicación publicada</span><span class="sxs-lookup"><span data-stu-id="4f324-146">Run the published app</span></span>

1. <span data-ttu-id="4f324-147">En el **Explorador**, haga clic con el botón derecho en la carpeta *publish* (o presione <kbd>Ctrl</kbd> y haga clic en macOS) y seleccione **Abrir en terminal**.</span><span class="sxs-lookup"><span data-stu-id="4f324-147">In **Explorer**, right-click the *publish* folder (<kbd>Ctrl</kbd>-click on macOS), and select **Open in Terminal**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="Menú contextual en el que se muestra la sección Abrir en terminal":::

1. <span data-ttu-id="4f324-149">En Windows o Linux, ejecute la aplicación con el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4f324-149">On Windows or Linux, run the app by using the executable.</span></span>

   1. <span data-ttu-id="4f324-150">En Windows, escriba `.\HelloWorld.exe` y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4f324-150">On Windows, enter `.\HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="4f324-151">En Linux, escriba `./HelloWorld` y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4f324-151">On Linux, enter `./HelloWorld` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="4f324-152">Escriba un nombre cuando se le pida y presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="4f324-152">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="4f324-153">En cualquier plataforma, ejecute la aplicación con el comando [`dotnet`](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="4f324-153">On any platform, run the app by using the  [`dotnet`](../tools/dotnet.md) command:</span></span>

   1. <span data-ttu-id="4f324-154">Escriba `dotnet HelloWorld.dll` y presione <kbd>ENTRAR</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4f324-154">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="4f324-155">Escriba un nombre cuando se le pida y presione cualquier tecla para salir.</span><span class="sxs-lookup"><span data-stu-id="4f324-155">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4f324-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4f324-156">Additional resources</span></span>

- [<span data-ttu-id="4f324-157">implementación de aplicaciones .NET</span><span class="sxs-lookup"><span data-stu-id="4f324-157">.NET application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="4f324-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4f324-158">Next steps</span></span>

<span data-ttu-id="4f324-159">En este tutorial, ha publicado una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="4f324-159">In this tutorial, you published a console app.</span></span> <span data-ttu-id="4f324-160">En el siguiente tutorial, creará una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="4f324-160">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f324-161">Creación de una biblioteca de clases de .NET con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4f324-161">Create a .NET class library using Visual Studio Code</span></span>](library-with-visual-studio-code.md)

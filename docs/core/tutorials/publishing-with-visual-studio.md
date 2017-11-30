---
title: "Publicación de la aplicación Hola a todos con Visual Studio 2017"
description: "La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación."
keywords: ".NET, .NET Core, aplicación de consola, publicación, implementación"
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.openlocfilehash: a3e5bda5c99144c9ab5bbaf5e2f5566261af4813
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="10869-104">Publicación de la aplicación Hola a todos con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="10869-104">Publish your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="10869-105">En [Compilación de una aplicación Hola a todos en C# con .NET Core en Visual Studio 2017](with-visual-studio.md) o [Compilación de una aplicación Hola a todos en Visual Basic con .NET Core en Visual Studio 2017](vb-with-visual-studio.md), ha compilado una aplicación de consola Hola a todos.</span><span class="sxs-lookup"><span data-stu-id="10869-105">In [Build a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio.md) or [Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="10869-106">En [Depuración de la aplicación Hola a todos en C# con Visual Studio 2017](debugging-with-visual-studio.md), la ha probado con el depurador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="10869-106">In [Debug your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="10869-107">Ahora que está seguro de que funciona como se esperaba, puede publicarla para que otros usuarios puedan ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="10869-107">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="10869-108">Al realizar la publicación, se crea el conjunto de archivos necesarios para ejecutar la aplicación; y puede implementarlos mediante su copia en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="10869-108">Publishing creates the set of files that are needed to run your application, and you can deploy the files by copying them to a target machine.</span></span>

<span data-ttu-id="10869-109">Para publicar y ejecutar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="10869-109">To publish and run your application:</span></span> 

1. <span data-ttu-id="10869-110">Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10869-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="10869-111">Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="10869-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/toolbar.png)

1. <span data-ttu-id="10869-113">Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="10869-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="10869-114">También puede seleccionar **Publicar Hola a todos** en el menú principal **Compilar** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="10869-114">You can also select **Publish HelloWorld** from the main Visual Studio **Build** menu.</span></span>

   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/publish1.png)


   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/publishwindow.png)

1. <span data-ttu-id="10869-117">Abra una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="10869-117">Open a console window.</span></span> <span data-ttu-id="10869-118">Por ejemplo, en el cuadro de texto **Escriba aquí para ejecutar la búsqueda** de la barra de tareas de Windows, escriba `Command Prompt` (o `cmd` para abreviar) y abra una ventana de consola seleccionando la aplicación de escritorio **Símbolo del sistema** o presionando Entrar si está seleccionada en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="10869-118">For example in the **Type here to search** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="10869-119">Vaya a la aplicación publicada en el subdirectorio `bin\release\PublishOutput` del directorio del proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10869-119">Navigate to the published application in the `bin\release\PublishOutput` subdirectory of your application's project directory.</span></span> <span data-ttu-id="10869-120">Como se muestra en la ilustración siguiente, el resultado publicado incluye los siguientes cuatro archivos:</span><span class="sxs-lookup"><span data-stu-id="10869-120">As the following figure shows, the published output includes the following four files:</span></span>

      * <span data-ttu-id="10869-121">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="10869-121">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="10869-122">Archivo de dependencias de tiempo de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10869-122">The application's runtime dependencies file.</span></span> <span data-ttu-id="10869-123">Define los componentes principales de .NET y las bibliotecas (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesitan para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10869-123">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run your application.</span></span> <span data-ttu-id="10869-124">Para obtener más información, consulte [archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="10869-124">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>
 
      * <span data-ttu-id="10869-125">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="10869-125">*HelloWorld.dll*</span></span>

         <span data-ttu-id="10869-126">El archivo que contiene la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10869-126">The file that contains your application.</span></span> <span data-ttu-id="10869-127">Es una biblioteca de vínculos dinámicos que se pueden ejecutar mediante la especificación de la `dotnet HelloWorld.dll` comando en una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="10869-127">It is a dynamic link library that can be executed by entering the `dotnet HelloWorld.dll` command in a console window.</span></span> 

      * <span data-ttu-id="10869-128">*HelloWorld.pdb* (opcional para la implementación)</span><span class="sxs-lookup"><span data-stu-id="10869-128">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="10869-129">Un archivo que contiene los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="10869-129">A file that contains debug symbols.</span></span> <span data-ttu-id="10869-130">No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10869-130">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="10869-131">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="10869-131">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="10869-132">Archivo de configuración de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="10869-132">The application's runtime configuration file.</span></span> <span data-ttu-id="10869-133">Identifica la versión de .NET Core que la aplicación se ha compilado.</span><span class="sxs-lookup"><span data-stu-id="10869-133">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="10869-134">Para obtener más información, consulte [archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="10869-134">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>  

   ![Ventana de la consola que muestra los archivos publicados](media/publishing-with-visual-studio/publishedfiles.png)

<span data-ttu-id="10869-136">El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecutará en cualquier plataforma compatible con .NET Core con .NET Core instalado en el sistema.</span><span class="sxs-lookup"><span data-stu-id="10869-136">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application will run on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="10869-137">Los usuarios pueden ejecutar la aplicación mediante la emisión del comando `dotnet HelloWorld.dll` desde una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="10869-137">Users can run your application by issuing the `dotnet HelloWorld.dll` command from a console window.</span></span>

<span data-ttu-id="10869-138">Para más información sobre cómo publicar e implementar aplicaciones de .NET Core, consulte [Implementación de aplicaciones .NET Core](../../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="10869-138">For more information on publishing and deploying .NET Core applications, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>

---
title: Requisitos previos para .NET Core en Windows
description: Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771953"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="58e18-103">Requisitos previos para .NET Core en Windows</span><span class="sxs-lookup"><span data-stu-id="58e18-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="58e18-104">En este artículo se muestran las versiones compatibles del sistema operativo para ejecutar aplicaciones .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="58e18-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="58e18-105">Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:</span><span class="sxs-lookup"><span data-stu-id="58e18-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="58e18-106">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="58e18-106">Command line</span></span>](./tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="58e18-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="58e18-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [<span data-ttu-id="58e18-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="58e18-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="58e18-109">Además, si desarrolla en Windows con Visual Studio, en la sección [Requisitos previos para desarrollar aplicaciones de .NET Core con Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio), puede encontrar más información sobre las versiones mínimas compatibles con el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="58e18-109">Also, if you're developing on Windows using Visual Studio, the [Prerequisites to develop .NET Core apps with Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="58e18-110">Sistemas operativos admitidos por .NET Core</span><span class="sxs-lookup"><span data-stu-id="58e18-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="58e18-111">Los artículos siguientes incluyen una lista completa de sistemas operativos de .NET Core compatibles por versión:</span><span class="sxs-lookup"><span data-stu-id="58e18-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="58e18-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="58e18-112">.NET Core 3.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="58e18-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="58e18-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="58e18-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="58e18-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

<span data-ttu-id="58e18-115">Para vínculos de descarga y más información, vaya a [Descargas de .NET](https://dotnet.microsoft.com/download) para descargar la versión más reciente o al [archivo de descargas de .NET](https://dotnet.microsoft.com/download/archives#dotnet-core) para versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="58e18-115">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="58e18-116">Dependencias de .NET Core</span><span class="sxs-lookup"><span data-stu-id="58e18-116">.NET Core dependencies</span></span>

<span data-ttu-id="58e18-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="58e18-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="58e18-118">A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="58e18-118">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="58e18-119">Al implementar una aplicación de .NET Core independiente.</span><span class="sxs-lookup"><span data-stu-id="58e18-119">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="58e18-120">Al compilar el producto desde el origen.</span><span class="sxs-lookup"><span data-stu-id="58e18-120">Building the product from source.</span></span>
* <span data-ttu-id="58e18-121">Al instalar .NET Core a través de un archivo *.zip*.</span><span class="sxs-lookup"><span data-stu-id="58e18-121">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="58e18-122">Esto puede incluir servidores de compilación, integración continua o implementación continua.</span><span class="sxs-lookup"><span data-stu-id="58e18-122">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="58e18-123">**Para Windows 8.1 y versiones anteriores o Windows Server 2012 R2 y versiones anteriores:**</span><span class="sxs-lookup"><span data-stu-id="58e18-123">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="58e18-124">Asegúrese de que la instalación de Windows está actualizada e incluye la revisión [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), que se puede instalar mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="58e18-124">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="58e18-125">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="58e18-125">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="58e18-126">**Para Windows 7 o Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="58e18-126">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="58e18-127">Además de KB2999226, asegúrese de que también tiene instalada [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="58e18-127">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="58e18-128">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="58e18-128">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a><span data-ttu-id="58e18-129">Requisitos previos para desarrollar aplicaciones de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="58e18-129">Prerequisites to develop .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="58e18-130">Aunque puede usar cualquier editor para desarrollar aplicaciones de .NET Core con el SDK de .NET Core, Visual Studio 2017 y las versiones posteriores proporcionan un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="58e18-130">Even though you can use any editor to develop .NET Core applications using the .NET Core SDK, Visual Studio 2017 and later versions provide an integrated development environment for .NET Core apps on Windows.</span></span>

<a name="vs-mapping"></a>

<span data-ttu-id="58e18-131">Cada versión de .NET Core requiere una versión mínima de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="58e18-131">Each .NET Core version has a minimum version of Visual Studio required.</span></span> <span data-ttu-id="58e18-132">Para comprobar la versión de Visual Studio, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="58e18-132">To verify your Visual Studio version:</span></span>

* <span data-ttu-id="58e18-133">En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="58e18-133">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
* <span data-ttu-id="58e18-134">En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.</span><span class="sxs-lookup"><span data-stu-id="58e18-134">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>

<span data-ttu-id="58e18-135">En la tabla siguiente se muestra la versión mínima de cada SDK:</span><span class="sxs-lookup"><span data-stu-id="58e18-135">The following table lists the minimum version for each SDK:</span></span>

| <span data-ttu-id="58e18-136">Versión del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="58e18-136">.NET Core SDK version</span></span> | <span data-ttu-id="58e18-137">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="58e18-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="58e18-138">3.0</span><span class="sxs-lookup"><span data-stu-id="58e18-138">3.0</span></span>                   | <span data-ttu-id="58e18-139">Visual Studio 2019, versión 16.3 o posterior.</span><span class="sxs-lookup"><span data-stu-id="58e18-139">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="58e18-140">2.2</span><span class="sxs-lookup"><span data-stu-id="58e18-140">2.2</span></span>                   | <span data-ttu-id="58e18-141">Visual Studio 2017, versión 15.9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="58e18-141">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="58e18-142">2.1</span><span class="sxs-lookup"><span data-stu-id="58e18-142">2.1</span></span>                   | <span data-ttu-id="58e18-143">Visual Studio 2017, versión 15.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="58e18-143">Visual Studio 2017 version 15.7 or higher.</span></span> |
| <span data-ttu-id="58e18-144">1.x</span><span class="sxs-lookup"><span data-stu-id="58e18-144">1.x</span></span>                   | <span data-ttu-id="58e18-145">Visual Studio 2017, versión 15.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="58e18-145">Visual Studio 2017 version 15.0 or higher.</span></span> |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="58e18-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="58e18-146">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="58e18-147">Para desarrollar aplicaciones de .NET Core en Visual Studio 2019 con el SDK de .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="58e18-147">To develop .NET Core apps in Visual Studio 2019 using the .NET Core 3.0 SDK:</span></span>

* <span data-ttu-id="58e18-148">[Descargue e instale Visual Studio 2019 versión 16.3 o una versión superior](/visualstudio/install/install-visual-studio) y seleccione una de las siguientes cargas de trabajo que incluye el SDK de .NET Core según el tipo de aplicación que esté desarrollando:</span><span class="sxs-lookup"><span data-stu-id="58e18-148">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) and select one of the following workloads that includes the .NET Core SDK, depending on the kind of application you're building:</span></span>

  * <span data-ttu-id="58e18-149">La carga de trabajo **Desarrollo multiplataforma de .NET Core** en la sección **Otros conjuntos de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="58e18-149">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
  * <span data-ttu-id="58e18-150">La carga de trabajo **Desarrollo de ASP.NET y web** en la sección **Web y nube**.</span><span class="sxs-lookup"><span data-stu-id="58e18-150">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
  * <span data-ttu-id="58e18-151">La carga de trabajo **Desarrollo de escritorio de .NET** en la sección **Windows**.</span><span class="sxs-lookup"><span data-stu-id="58e18-151">The **NET desktop development** workload in the **Windows** section.</span></span>

<span data-ttu-id="58e18-152">En la siguiente imagen se muestra la carga de trabajo **Desarrollo multiplataforma de .NET Core** seleccionada en la interfaz de usuario de Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="58e18-152">The following image shows the **.NET Core cross-platform development** workload selected in the Visual Studio UI:</span></span>

![Captura de pantalla de la instalación de Visual Studio 2019 con la carga de trabajo “Desarrollo multiplataforma de .NET Core” seleccionada](./media/windows-prerequisites/vs-2019-workloads.jpg)

<span data-ttu-id="58e18-154">La versión 16.3 de Visual Studio 2019 usa el SDK de .NET Core 3.0 de manera predeterminada una vez que se instala cualquiera de estas cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="58e18-154">Visual Studio 2019 version 16.3 uses .NET Core 3.0 SDK by default after any of these workloads are installed.</span></span>

<span data-ttu-id="58e18-155">Si quiere que sus proyectos existentes usen el runtime de .NET Core más reciente, redestine cada uno de los proyectos de .NET Core existentes a .NET Core 3.0 según las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="58e18-155">If you want your existing projects to use the latest .NET Core runtime, retarget each existing .NET Core project to .NET Core 3.0 using the following instructions:</span></span>

* <span data-ttu-id="58e18-156">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="58e18-156">On the **Project** menu, choose **Properties**.</span></span>
* <span data-ttu-id="58e18-157">En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="58e18-157">In the **Target framework** selection menu, set the value to **.NET Core 3.0**.</span></span>

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2019 con el elemento de menú Plataforma de destino “.NET Core 3.0” seleccionado](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

<span data-ttu-id="58e18-159">Una vez que Visual Studio está configurado con el SDK de .NET Core 3.0, puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="58e18-159">Once you have Visual Studio configured with .NET Core 3.0 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="58e18-160">Abrir, compilar y ejecutar proyectos de .NET Core 1.x y 2.x existentes.</span><span class="sxs-lookup"><span data-stu-id="58e18-160">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="58e18-161">Redestinar proyectos de .NET Core 1.x y 2.x a .NET Core 3.0, compilarlos y ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="58e18-161">Retarget .NET Core 1.x and 2.x projects to .NET Core 3.0, build, and run.</span></span>
* <span data-ttu-id="58e18-162">Crear proyectos de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="58e18-162">Create new .NET Core 3.0 projects.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="58e18-163">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="58e18-163">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="58e18-164">Para desarrollar aplicaciones .NET Core en Visual Studio 2017 con el SDK de .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="58e18-164">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

* <span data-ttu-id="58e18-165">[Descargue e instale Visual Studio 2019 versión 16.3 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="58e18-165">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
* <span data-ttu-id="58e18-166">[Descargue e instale Visual Studio 2017 versión 15.9.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="58e18-166">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="58e18-168">Una vez instalado el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio habitualmente instala una versión anterior del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="58e18-168">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="58e18-169">Por ejemplo, la versión 15.9 de Visual Studio 2017 usa el SDK de .NET Core 2.1 de manera predeterminada una vez que se instala la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="58e18-169">For example, Visual Studio 2017 version 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="58e18-170">Para actualizar Visual Studio para que use el SDK de .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="58e18-170">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="58e18-171">Instale el [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="58e18-171">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="58e18-172">Si quiere que el proyecto use el runtime de .NET Core más reciente, redestine cada uno de los proyectos de .NET Core nuevos o existentes a .NET Core 2.2 según las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="58e18-172">If you want your project to use the latest .NET Core runtime, retarget each existing or new .NET Core project to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="58e18-173">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="58e18-173">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="58e18-174">En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.2**.</span><span class="sxs-lookup"><span data-stu-id="58e18-174">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino ".NET Core 2.2" seleccionado](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="58e18-176">Una vez que Visual Studio está configurado con el SDK de .NET Core 2.2, puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="58e18-176">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="58e18-177">Abrir, compilar y ejecutar proyectos de .NET Core 1.x y 2.x existentes.</span><span class="sxs-lookup"><span data-stu-id="58e18-177">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="58e18-178">Redestinar proyectos de .NET Core 1.x y 2.x a .NET Core 2.2, compilarlos y ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="58e18-178">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="58e18-179">Crear proyectos de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="58e18-179">Create new .NET Core 2.2 projects.</span></span>

---

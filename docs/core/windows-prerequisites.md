---
title: Requisitos previos para .NET Core en Windows
description: Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core.
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 7b2bf2b8353c4f02fa11e9e7531e0d936007be0b
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70970281"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="c25ce-103">Requisitos previos para .NET Core en Windows</span><span class="sxs-lookup"><span data-stu-id="c25ce-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="c25ce-104">En este artículo se muestran las versiones compatibles del sistema operativo para ejecutar aplicaciones .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="c25ce-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="c25ce-105">Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:</span><span class="sxs-lookup"><span data-stu-id="c25ce-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="c25ce-106">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c25ce-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="c25ce-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c25ce-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [<span data-ttu-id="c25ce-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c25ce-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="c25ce-109">También, si desarrolla en Windows con Visual Studio 2017, en la sección [Requisitos previos con Visual Studio 2017](#prerequisites-with-visual-studio-2017) puede encontrar más detalles sobre las versiones mínimas compatibles con el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c25ce-109">Also, if you're developing on Windows using Visual Studio 2017, the [Prerequisites with Visual Studio 2017](#prerequisites-with-visual-studio-2017) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="c25ce-110">Sistemas operativos admitidos por .NET Core</span><span class="sxs-lookup"><span data-stu-id="c25ce-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="c25ce-111">Los artículos siguientes incluyen una lista completa de sistemas operativos de .NET Core compatibles por versión:</span><span class="sxs-lookup"><span data-stu-id="c25ce-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="c25ce-112">.NET Core 3.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c25ce-112">.NET Core 3.0 (Preview)</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="c25ce-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c25ce-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="c25ce-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c25ce-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="c25ce-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c25ce-115">.NET Core 1.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

<span data-ttu-id="c25ce-116">Para vínculos de descarga y más información, vaya a [Descargas de .NET](https://dotnet.microsoft.com/download) para descargar la versión más reciente o al [archivo de descargas de .NET](https://dotnet.microsoft.com/download/archives#dotnet-core) para versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="c25ce-116">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="c25ce-117">Dependencias de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c25ce-117">.NET Core dependencies</span></span>

<span data-ttu-id="c25ce-118">.NET Core 1.1 y versiones anteriores requieren Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c25ce-118">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="c25ce-119">Esta dependencia se instala automáticamente si usa el instalador de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c25ce-119">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="c25ce-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="c25ce-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="c25ce-121">A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="c25ce-121">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="c25ce-122">Al implementar una aplicación de .NET Core independiente.</span><span class="sxs-lookup"><span data-stu-id="c25ce-122">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="c25ce-123">Al compilar el producto desde el origen.</span><span class="sxs-lookup"><span data-stu-id="c25ce-123">Building the product from source.</span></span>
* <span data-ttu-id="c25ce-124">Al instalar .NET Core a través de un archivo *.zip*.</span><span class="sxs-lookup"><span data-stu-id="c25ce-124">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="c25ce-125">Esto puede incluir servidores de compilación, integración continua o implementación continua.</span><span class="sxs-lookup"><span data-stu-id="c25ce-125">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="c25ce-126">**Para Windows 8.1 y versiones anteriores o Windows Server 2012 R2 y versiones anteriores:**</span><span class="sxs-lookup"><span data-stu-id="c25ce-126">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="c25ce-127">Asegúrese de que la instalación de Windows está actualizada e incluye la revisión [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), que se puede instalar mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="c25ce-127">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="c25ce-128">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="c25ce-128">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="c25ce-129">**Para Windows 7 o Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="c25ce-129">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="c25ce-130">Además de KB2999226, asegúrese de que también tiene instalada [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="c25ce-130">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="c25ce-131">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="c25ce-131">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-for-net-core-30-preview-3"></a><span data-ttu-id="c25ce-132">Requisitos previos para la versión preliminar 3 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c25ce-132">Prerequisites for .NET Core 3.0 Preview 3</span></span>

<span data-ttu-id="c25ce-133">La versión preliminar 3 de .NET Core 3.0 tiene los mismos requisitos previos que otras versiones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c25ce-133">.NET Core 3.0 Preview 3 has the same prerequisites as other versions of .NET Core.</span></span> <span data-ttu-id="c25ce-134">Pero si quiere usar Visual Studio para crear proyectos de .NET Core 3.0, debe usar [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="c25ce-134">However, if you want to use Visual Studio to create .NET Core 3.0 projects, you must use the [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="c25ce-135">Visual Studio 2019 se puede instalar en paralelo con otras versiones de Visual Studio sin conflictos.</span><span class="sxs-lookup"><span data-stu-id="c25ce-135">Visual Studio 2019 can be installed side-by-side with other versions of Visual Studio without conflict.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="c25ce-136">Requisitos previos con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c25ce-136">Prerequisites with Visual Studio 2017</span></span>
    
<span data-ttu-id="c25ce-137">Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c25ce-137">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="c25ce-138">Visual Studio 2017 proporciona un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="c25ce-138">Visual Studio 2017 provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="c25ce-139">Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="c25ce-139">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c25ce-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c25ce-140">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="c25ce-141">Para desarrollar aplicaciones .NET Core en Visual Studio 2017 con el SDK de .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="c25ce-141">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="c25ce-142">[Descargue e instale Visual Studio 2017 versión 15.9.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c25ce-142">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="c25ce-144">Una vez instalado el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio habitualmente instala una versión anterior del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c25ce-144">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="c25ce-145">Por ejemplo, Visual Studio 2017 15.9 usa el SDK de .NET Core 2.1 de manera predeterminada una vez que se instala la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c25ce-145">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="c25ce-146">Para actualizar Visual Studio para que use el SDK de .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="c25ce-146">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="c25ce-147">Instale el [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="c25ce-147">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="c25ce-148">Si quiere que el proyecto use el entorno de ejecución de .NET Core más reciente, redestine los proyectos de .NET Core nuevos o existentes a .NET Core 2.2 según las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c25ce-148">If you want your project to use the latest .NET Core runtime, retarget existing or new .NET Core projects to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="c25ce-149">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c25ce-149">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="c25ce-150">En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.2**.</span><span class="sxs-lookup"><span data-stu-id="c25ce-150">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino ".NET Core 2.2" seleccionado](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="c25ce-152">Una vez que Visual Studio está configurado con el SDK de .NET Core 2.2, puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c25ce-152">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="c25ce-153">Abrir, compilar y ejecutar proyectos de .NET Core 1.x y 2.x existentes.</span><span class="sxs-lookup"><span data-stu-id="c25ce-153">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="c25ce-154">Redestinar proyectos de .NET Core 1.x y 2.x a .NET Core 2.2, compilarlos y ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="c25ce-154">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="c25ce-155">Crear proyectos de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="c25ce-155">Create new .NET Core 2.2 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c25ce-156">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c25ce-156">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c25ce-157">Para desarrollar aplicaciones de .NET Core 1.x en Visual Studio, [descargue e instale Visual Studio 2017](/visualstudio/install/install-visual-studio) con la carga de trabajo **"Desarrollo multiplataforma de .NET Core"** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c25ce-157">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="c25ce-159">Es posible usar Visual Studio 2015 para el desarrollo con .NET Core 1.x, pero no se recomienda por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c25ce-159">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
>
> * <span data-ttu-id="c25ce-160">Las herramientas de .NET Core están en versión preliminar, lo que no es compatible.</span><span class="sxs-lookup"><span data-stu-id="c25ce-160">The .NET Core tooling is a preview version, which is not supported.</span></span>
> * <span data-ttu-id="c25ce-161">Los proyectos están basados en project.json, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="c25ce-161">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="c25ce-162">Para obtener más información sobre los cambios de formato de proyecto, consulte [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Información general de alto nivel sobre los cambios).</span><span class="sxs-lookup"><span data-stu-id="c25ce-162">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="c25ce-163">Para comprobar la versión de Visual Studio, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c25ce-163">To verify your Visual Studio version:</span></span>
>
> * <span data-ttu-id="c25ce-164">En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="c25ce-164">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="c25ce-165">En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.</span><span class="sxs-lookup"><span data-stu-id="c25ce-165">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="c25ce-166">Para las aplicaciones de la versión preliminar 3 de .NET Core 3.0, la versión 16.0 o superior de Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c25ce-166">For .NET Core 3.0 Preview 3 apps, Visual Studio 2019 version 16.0 or higher.</span></span>
>   * <span data-ttu-id="c25ce-167">Para las aplicaciones de .NET Core 2.2, debe ser Visual Studio 2017 versión 15.9 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="c25ce-167">For .NET Core 2.2 apps, Visual Studio 2017 version 15.9 or higher.</span></span>
>   * <span data-ttu-id="c25ce-168">Para las aplicaciones de .NET Core 2.1, debe ser Visual Studio 2017 versión 15.7 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="c25ce-168">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="c25ce-169">Para las aplicaciones de .NET Core 1.x, debe ser Visual Studio 2017 versión 15.0 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="c25ce-169">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>

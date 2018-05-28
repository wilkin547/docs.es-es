---
title: Requisitos previos para .NET Core en Windows
description: Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core.
author: JRAlexander
ms.author: johalex
ms.date: 05/18/2018
ms.openlocfilehash: 3d172c83f0a79744afbaeeff52d7fea62d9b98b6
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="09428-103">Requisitos previos para .NET Core en Windows</span><span class="sxs-lookup"><span data-stu-id="09428-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="09428-104">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="09428-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="09428-105">Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:</span><span class="sxs-lookup"><span data-stu-id="09428-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="09428-106">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="09428-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="09428-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="09428-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="09428-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="09428-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="09428-109">Versiones admitidas de Windows de .NET Core</span><span class="sxs-lookup"><span data-stu-id="09428-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="09428-110">.NET Core es compatible con las siguientes versiones de:</span><span class="sxs-lookup"><span data-stu-id="09428-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="09428-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="09428-111">Windows 7 SP1</span></span>
* <span data-ttu-id="09428-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="09428-112">Windows 8.1</span></span>
* <span data-ttu-id="09428-113">Actualización de aniversario de Windows 10 (versión 1607) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="09428-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="09428-114">Windows Server 2008 R2 SP1 (Servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="09428-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="09428-115">Windows Server 2012 SP1 (Servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="09428-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="09428-116">Windows Server 2012 R2 (servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="09428-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="09428-117">Windows Server 2016 o versiones posteriores (Servidor completo, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="09428-117">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="09428-118">Los artículos siguientes incluyen una lista completa de sistemas operativos de .NET Core compatibles por versión:</span><span class="sxs-lookup"><span data-stu-id="09428-118">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="09428-119">.NET Core 2.1: versiones de sistema operativo compatibles</span><span class="sxs-lookup"><span data-stu-id="09428-119">.NET Core 2.1 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="09428-120">.NET Core 2.0: versiones de sistema operativo compatibles</span><span class="sxs-lookup"><span data-stu-id="09428-120">.NET Core 2.0 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [<span data-ttu-id="09428-121">.NET Core 1.x: versiones de sistema operativo compatibles</span><span class="sxs-lookup"><span data-stu-id="09428-121">.NET Core 1.x - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a><span data-ttu-id="09428-122">Dependencias de .NET Core</span><span class="sxs-lookup"><span data-stu-id="09428-122">.NET Core dependencies</span></span>

<span data-ttu-id="09428-123">.NET Core 1.1 y versiones anteriores requieren Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="09428-123">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="09428-124">Esta dependencia se instala automáticamente si usa el instalador de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09428-124">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="09428-125">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="09428-125">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="09428-126">A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="09428-126">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="09428-127">Al implementar una aplicación de .NET Core independiente.</span><span class="sxs-lookup"><span data-stu-id="09428-127">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="09428-128">Al compilar el producto desde el origen.</span><span class="sxs-lookup"><span data-stu-id="09428-128">Building the product from source.</span></span>
* <span data-ttu-id="09428-129">Al instalar .NET Core a través de un archivo *.zip*.</span><span class="sxs-lookup"><span data-stu-id="09428-129">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="09428-130">Esto puede incluir servidores de compilación, integración continua o implementación continua.</span><span class="sxs-lookup"><span data-stu-id="09428-130">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="09428-131">**Para Windows 8.1 y versiones anteriores o Windows Server 2012 R2 y versiones anteriores:**</span><span class="sxs-lookup"><span data-stu-id="09428-131">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="09428-132">Asegúrese de que la instalación de Windows está actualizada e incluye la revisión [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), que se puede instalar mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="09428-132">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="09428-133">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="09428-133">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="09428-134">**Para Windows 7 o Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="09428-134">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="09428-135">Además de KB2999226, asegúrese de que también tiene instalada [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="09428-135">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="09428-136">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="09428-136">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="09428-137">Requisitos previos con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="09428-137">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="09428-138">Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09428-138">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="09428-139">[Visual Studio 2017](#visual-studio-2017) proporciona un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="09428-139">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="09428-140">Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="09428-140">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="09428-141">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="09428-141">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="09428-142">Para desarrollar aplicaciones de .NET Core 2.x en Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="09428-142">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="09428-143">[Descargue e instale Visual Studio 2017 versión 15.3.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="09428-143">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="09428-145">Después de instalar el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio 2017 usará .NET Core 1.x de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="09428-145">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="09428-146">Instale el SDK de .NET Core 2.x para obtener compatibilidad con .NET Core 2.x en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="09428-146">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="09428-147">Instale el [SDK de .NET Core 2.x](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="09428-147">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="09428-148">Redestine los proyectos de .NET Core 1.x nuevos o existentes a .NET Core 2.x siguiendo estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="09428-148">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="09428-149">En el menú **Proyecto**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="09428-149">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="09428-150">En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="09428-150">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino “.NET Core 2.0” seleccionado](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="09428-152">Una vez haya instalado el SDK de .NET Core 2.x, Visual Studio 2017 usará el SDK de .NET Core 2.x de manera predeterminada y admitirá las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="09428-152">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

* <span data-ttu-id="09428-153">Apertura, compilación y ejecución de proyectos de .NET Core 1.x existentes.</span><span class="sxs-lookup"><span data-stu-id="09428-153">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="09428-154">Redestinación de proyectos de .NET Core 1.x a .NET Core 2.x, compilación y ejecución.</span><span class="sxs-lookup"><span data-stu-id="09428-154">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
* <span data-ttu-id="09428-155">Creación de proyectos de .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="09428-155">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="09428-156">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="09428-156">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="09428-157">Para desarrollar aplicaciones de .NET Core 1.x en Visual Studio, [descargue e instale Visual Studio 2017 RTM (versión 15.0.26228.4) o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **“desarrollo multiplataforma de .NET Core”** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="09428-157">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="09428-159">Es posible usar Visual Studio 2015 para el desarrollo con .NET Core 1.x, pero no se recomienda por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="09428-159">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="09428-160">Las herramientas de .NET Core están en versión preliminar, lo que no es compatible.</span><span class="sxs-lookup"><span data-stu-id="09428-160">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="09428-161">Los proyectos están basados en project.json, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="09428-161">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="09428-162">Para obtener más información sobre los cambios de formato de proyecto, consulte [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Información general de alto nivel sobre los cambios).</span><span class="sxs-lookup"><span data-stu-id="09428-162">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

> [!TIP]
> <span data-ttu-id="09428-163">Para comprobar la versión de Visual Studio 2017, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09428-163">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="09428-164">En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="09428-164">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="09428-165">En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.</span><span class="sxs-lookup"><span data-stu-id="09428-165">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="09428-166">Para aplicaciones de .NET Core 2.1 RC, debe ser Visual Studio 2017 versión 15.7 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="09428-166">For .NET Core 2.1 RC apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="09428-167">Para las aplicaciones de .NET Core 2.0, debe ser Visual Studio 2017 versión 15.3 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="09428-167">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="09428-168">Para las aplicaciones de .NET Core 1.x, debe ser Visual Studio 2017 versión 15.0 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="09428-168">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>

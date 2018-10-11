---
title: Requisitos previos para .NET Core en Windows
description: Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: 63c0de2b413f38458dba89506f4070760b3f53f8
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45747473"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="f01a7-103">Requisitos previos para .NET Core en Windows</span><span class="sxs-lookup"><span data-stu-id="f01a7-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="f01a7-104">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="f01a7-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="f01a7-105">Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:</span><span class="sxs-lookup"><span data-stu-id="f01a7-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="f01a7-106">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f01a7-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="f01a7-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f01a7-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="f01a7-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f01a7-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="f01a7-109">Versiones admitidas de Windows de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f01a7-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="f01a7-110">.NET Core es compatible con las siguientes versiones de:</span><span class="sxs-lookup"><span data-stu-id="f01a7-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="f01a7-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="f01a7-111">Windows 7 SP1</span></span>
* <span data-ttu-id="f01a7-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f01a7-112">Windows 8.1</span></span>
* <span data-ttu-id="f01a7-113">Actualización de aniversario de Windows 10 (versión 1607) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f01a7-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="f01a7-114">Windows Server 2008 R2 SP1 (Servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="f01a7-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="f01a7-115">Windows Server 2012 SP1 (Servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="f01a7-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="f01a7-116">Windows Server 2012 R2 (servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="f01a7-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="f01a7-117">Windows Server 2016 o versiones posteriores (Servidor completo, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="f01a7-117">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="f01a7-118">Sistemas operativos admitidos por .NET Core</span><span class="sxs-lookup"><span data-stu-id="f01a7-118">.NET Core supported operating systems</span></span>

<span data-ttu-id="f01a7-119">Los artículos siguientes incluyen una lista completa de sistemas operativos de .NET Core compatibles por versión:</span><span class="sxs-lookup"><span data-stu-id="f01a7-119">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="f01a7-120">.NET Core 2.1: versiones de sistema operativo compatibles</span><span class="sxs-lookup"><span data-stu-id="f01a7-120">.NET Core 2.1 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="f01a7-121">.NET Core 2.0: versiones de sistema operativo compatibles</span><span class="sxs-lookup"><span data-stu-id="f01a7-121">.NET Core 2.0 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [<span data-ttu-id="f01a7-122">.NET Core 1.x: versiones de sistema operativo compatibles</span><span class="sxs-lookup"><span data-stu-id="f01a7-122">.NET Core 1.x - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a><span data-ttu-id="f01a7-123">Dependencias de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f01a7-123">.NET Core dependencies</span></span>

<span data-ttu-id="f01a7-124">.NET Core 1.1 y versiones anteriores requieren Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="f01a7-124">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="f01a7-125">Esta dependencia se instala automáticamente si usa el instalador de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f01a7-125">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="f01a7-126">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="f01a7-126">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="f01a7-127">A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f01a7-127">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="f01a7-128">Al implementar una aplicación de .NET Core independiente.</span><span class="sxs-lookup"><span data-stu-id="f01a7-128">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="f01a7-129">Al compilar el producto desde el origen.</span><span class="sxs-lookup"><span data-stu-id="f01a7-129">Building the product from source.</span></span>
* <span data-ttu-id="f01a7-130">Al instalar .NET Core a través de un archivo *.zip*.</span><span class="sxs-lookup"><span data-stu-id="f01a7-130">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="f01a7-131">Esto puede incluir servidores de compilación, integración continua o implementación continua.</span><span class="sxs-lookup"><span data-stu-id="f01a7-131">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="f01a7-132">**Para Windows 8.1 y versiones anteriores o Windows Server 2012 R2 y versiones anteriores:**</span><span class="sxs-lookup"><span data-stu-id="f01a7-132">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="f01a7-133">Asegúrese de que la instalación de Windows está actualizada e incluye la revisión [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), que se puede instalar mediante Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f01a7-133">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="f01a7-134">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="f01a7-134">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="f01a7-135">**Para Windows 7 o Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="f01a7-135">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="f01a7-136">Además de KB2999226, asegúrese de que también tiene instalada [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="f01a7-136">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="f01a7-137">Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="f01a7-137">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="f01a7-138">Requisitos previos con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f01a7-138">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="f01a7-139">Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f01a7-139">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="f01a7-140">Visual Studio 2017 proporciona un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="f01a7-140">Visual Studio 2017 provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="f01a7-141">Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="f01a7-141">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f01a7-142">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f01a7-142">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="f01a7-143">Para desarrollar aplicaciones de .NET Core 2.1 en Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="f01a7-143">To develop .NET Core 2.1 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="f01a7-144">[Descargue e instale Visual Studio 2017 versión 15.7.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f01a7-144">[Download and install Visual Studio 2017 version 15.7.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-15-8-workloads.jpg)

<span data-ttu-id="f01a7-146">Después de instalar el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio 2017 15.7 usará el SDK de .NET Core 2.0 y Visual Studio 2017 15.8 usará el SDK 2.1 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f01a7-146">After the **.NET Core cross-platform development** toolset is installed, by default, Visual Studio 2017 15.7 uses .NET Core 2.0 SDK and Visual Studio 2017 15.8 uses 2.1 SDK.</span></span>

 2. <span data-ttu-id="f01a7-147">Si usa Visual Studio 2017 15.7, instale el [SDK de .NET Core 2.1](https://www.microsoft.com/net/download/core) o una actualización a Visual Studio 2017 15.8.</span><span class="sxs-lookup"><span data-stu-id="f01a7-147">If you're using Visual Studio 2017 15.7, install the [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) or upgrade to Visual Studio 2017 15.8.</span></span>

 3. <span data-ttu-id="f01a7-148">Redestine los proyectos de .NET Core nuevos o existentes a .NET Core 2.1 siguiendo estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="f01a7-148">Retarget existing or new .NET Core projects to .NET Core 2.1 using the following instructions:</span></span>
    * <span data-ttu-id="f01a7-149">En el menú **Proyecto**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f01a7-149">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="f01a7-150">En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.1**.</span><span class="sxs-lookup"><span data-stu-id="f01a7-150">In the **Target framework** selection menu, set the value to **.NET Core 2.1**.</span></span>

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino “.NET Core 2.0” seleccionado](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="f01a7-152">Una vez que Visual Studio está configurado con el SDK de .NET Core 2.1, puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f01a7-152">Once you have Visual Studio configured with .NET Core 2.1 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="f01a7-153">Abrir, compilar y ejecutar proyectos de .NET Core 1.x y 2.x existentes.</span><span class="sxs-lookup"><span data-stu-id="f01a7-153">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="f01a7-154">Redestinar proyectos de .NET Core 1.x y 2.0 a .NET Core 2.1, compilarlos y ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="f01a7-154">Retarget .NET Core 1.x and 2.0 projects to .NET Core 2.1, build, and run.</span></span>
* <span data-ttu-id="f01a7-155">Crear proyectos de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="f01a7-155">Create new .NET Core 2.1 projects.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f01a7-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f01a7-156">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="f01a7-157">Para desarrollar aplicaciones de .NET Core 2.0 en Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="f01a7-157">To develop .NET Core 2.0 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="f01a7-158">[Descargue e instale Visual Studio 2017 versión 15.3.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f01a7-158">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="f01a7-160">Después de instalar el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio 2017 usará .NET Core 1.x de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f01a7-160">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="f01a7-161">Instale el SDK de .NET Core 2.0 para obtener compatibilidad con .NET Core 2.0 en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f01a7-161">Install the .NET Core 2.0 SDK to get .NET Core 2.0 support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="f01a7-162">Instale el [SDK de .NET Core 2.0](https://www.microsoft.com/net/download/dotnet-core/2.0).</span><span class="sxs-lookup"><span data-stu-id="f01a7-162">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).</span></span>
 3. <span data-ttu-id="f01a7-163">Redestine los proyectos de .NET Core 1.x nuevos o existentes a .NET Core 2.0 siguiendo estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="f01a7-163">Retarget existing or new .NET Core 1.x projects to .NET Core 2.0 using the following instructions:</span></span>
    * <span data-ttu-id="f01a7-164">En el menú **Proyecto**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f01a7-164">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="f01a7-165">En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="f01a7-165">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino “.NET Core 2.0” seleccionado](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="f01a7-167">Una vez haya instalado el SDK de .NET Core 2.0, Visual Studio 2017 usará el SDK de .NET Core 2.0 de manera predeterminada y admitirá las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f01a7-167">Once the .NET Core 2.0 SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.0 by default, and supports the following actions:</span></span>

* <span data-ttu-id="f01a7-168">Apertura, compilación y ejecución de proyectos de .NET Core 1.x existentes.</span><span class="sxs-lookup"><span data-stu-id="f01a7-168">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="f01a7-169">Redestinar proyectos de .NET Core 1.x a .NET Core 2.0, compilarlos y ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="f01a7-169">Retarget .NET Core 1.x projects to .NET Core 2.0, build, and run.</span></span>
* <span data-ttu-id="f01a7-170">Crear proyectos de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="f01a7-170">Create new .NET Core 2.0 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f01a7-171">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f01a7-171">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f01a7-172">Para desarrollar aplicaciones de .NET Core 1.x en Visual Studio, [descargue e instale Visual Studio 2017](/visualstudio/install/install-visual-studio) con la carga de trabajo **"Desarrollo multiplataforma de .NET Core"** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f01a7-172">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="f01a7-174">Es posible usar Visual Studio 2015 para el desarrollo con .NET Core 1.x, pero no se recomienda por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f01a7-174">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="f01a7-175">Las herramientas de .NET Core están en versión preliminar, lo que no es compatible.</span><span class="sxs-lookup"><span data-stu-id="f01a7-175">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="f01a7-176">Los proyectos están basados en project.json, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="f01a7-176">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="f01a7-177">Para obtener más información sobre los cambios de formato de proyecto, consulte [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Información general de alto nivel sobre los cambios).</span><span class="sxs-lookup"><span data-stu-id="f01a7-177">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="f01a7-178">Para comprobar la versión de Visual Studio 2017, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f01a7-178">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="f01a7-179">En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="f01a7-179">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="f01a7-180">En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.</span><span class="sxs-lookup"><span data-stu-id="f01a7-180">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="f01a7-181">Para las aplicaciones de .NET Core 2.2 Preview 1, Visual Studio 2017 versión 15.9 (actualmente en versión preliminar) o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="f01a7-181">For .NET Core 2.2 Preview 1 apps, Visual Studio 2017 version 15.9 (currently in Preview) or higher.</span></span>
>   * <span data-ttu-id="f01a7-182">Para las aplicaciones de .NET Core 2.1, debe ser Visual Studio 2017 versión 15.7 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="f01a7-182">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="f01a7-183">Para las aplicaciones de .NET Core 2.0, debe ser Visual Studio 2017 versión 15.3 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="f01a7-183">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="f01a7-184">Para las aplicaciones de .NET Core 1.x, debe ser Visual Studio 2017 versión 15.0 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="f01a7-184">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>

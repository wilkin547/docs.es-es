---
title: Requisitos previos para .NET Core en Windows
description: "Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core."
author: JRAlexander
ms.author: johalex
ms.date: 03/02/2018
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 48102f3fb7fa6e93238eefff0e7f1ecbed4d8409
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="5080f-103">Requisitos previos para .NET Core en Windows</span><span class="sxs-lookup"><span data-stu-id="5080f-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="5080f-104">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="5080f-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="5080f-105">Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:</span><span class="sxs-lookup"><span data-stu-id="5080f-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="5080f-106">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5080f-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="5080f-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5080f-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="5080f-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5080f-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="5080f-109">Versiones admitidas de Windows de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5080f-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="5080f-110">.NET Core es compatible con las siguientes versiones de:</span><span class="sxs-lookup"><span data-stu-id="5080f-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="5080f-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="5080f-111">Windows 7 SP1</span></span>
* <span data-ttu-id="5080f-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5080f-112">Windows 8.1</span></span>
* <span data-ttu-id="5080f-113">Actualización de aniversario de Windows 10 (versión 1607) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="5080f-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="5080f-114">Windows Server 2008 R2 SP1 (Servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="5080f-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="5080f-115">Windows Server 2012 SP1 (Servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="5080f-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="5080f-116">Windows Server 2012 R2 (servidor completo o Server Core)</span><span class="sxs-lookup"><span data-stu-id="5080f-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="5080f-117">Windows Server 2016 (Servidor completo, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="5080f-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="5080f-118">Vea el artículo [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="5080f-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="5080f-119">Vea el artículo [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="5080f-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="5080f-120">Dependencias de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5080f-120">.NET Core dependencies</span></span>

<span data-ttu-id="5080f-121">.NET Core 1.1 y versiones anteriores requieren Visual C++ Redistributable cuando se ejecuta en versiones de Windows anteriores a Windows 10 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="5080f-121">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="5080f-122">Esta dependencia se instala automáticamente si usa el instalador de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5080f-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="5080f-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="5080f-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="5080f-124">A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="5080f-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="5080f-125">Al implementar una aplicación de .NET Core independiente.</span><span class="sxs-lookup"><span data-stu-id="5080f-125">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="5080f-126">Al compilar el producto desde el origen.</span><span class="sxs-lookup"><span data-stu-id="5080f-126">Building the product from source.</span></span>
* <span data-ttu-id="5080f-127">Al instalar .NET Core a través de un archivo *.zip*.</span><span class="sxs-lookup"><span data-stu-id="5080f-127">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="5080f-128">Esto puede incluir servidores de compilación, integración continua o implementación continua.</span><span class="sxs-lookup"><span data-stu-id="5080f-128">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="5080f-129">*Solo para equipos con Windows 7 y Windows Server 2008:* asegúrese de que la instalación de Windows está actualizada y que incluye la revisión [KB2533623](https://support.microsoft.com/help/2533623) instalada a través de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5080f-129">*For Windows 7 and Windows Server 2008 machines only:* Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="5080f-130">Requisitos previos con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5080f-130">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="5080f-131">Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5080f-131">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="5080f-132">[Visual Studio 2017](#visual-studio-2017) proporciona un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.</span><span class="sxs-lookup"><span data-stu-id="5080f-132">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="5080f-133">Puede leer más sobre los cambios en Visual Studio 2017 en las [notas de la versión](/visualstudio/releasenotes/vs2017-relnotes).</span><span class="sxs-lookup"><span data-stu-id="5080f-133">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="5080f-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5080f-134">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="5080f-135">Para desarrollar aplicaciones de .NET Core 2.x en Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="5080f-135">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="5080f-136">[Descargue e instale Visual Studio 2017 versión 15.3.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5080f-136">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="5080f-138">Después de instalar el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio 2017 usará .NET Core 1.x de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5080f-138">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="5080f-139">Instale el SDK de .NET Core 2.x para obtener compatibilidad con .NET Core 2.x en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5080f-139">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="5080f-140">Instale el [SDK de .NET Core 2.x](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="5080f-140">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="5080f-141">Redestine los proyectos de .NET Core 1.x nuevos o existentes a .NET Core 2.x siguiendo estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="5080f-141">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="5080f-142">En el menú **Proyecto**, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5080f-142">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="5080f-143">En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="5080f-143">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino “.NET Core 2.0” seleccionado](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="5080f-145">Una vez haya instalado el SDK de .NET Core 2.x, Visual Studio 2017 usará el SDK de .NET Core 2.x de manera predeterminada y admitirá las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5080f-145">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

* <span data-ttu-id="5080f-146">Apertura, compilación y ejecución de proyectos de .NET Core 1.x existentes.</span><span class="sxs-lookup"><span data-stu-id="5080f-146">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="5080f-147">Redestinación de proyectos de .NET Core 1.x a .NET Core 2.x, compilación y ejecución.</span><span class="sxs-lookup"><span data-stu-id="5080f-147">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
* <span data-ttu-id="5080f-148">Creación de proyectos de .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="5080f-148">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5080f-149">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5080f-149">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5080f-150">Para desarrollar aplicaciones de .NET Core 1.x en Visual Studio, [descargue e instale Visual Studio 2017 RTM (versión 15.0.26228.4) o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **“desarrollo multiplataforma de .NET Core”** (en la sección **Otros conjuntos de herramientas**) seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5080f-150">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="5080f-152">Es posible usar Visual Studio 2015 para el desarrollo con .NET Core 1.x, pero no se recomienda por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5080f-152">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="5080f-153">Las herramientas de .NET Core están en versión preliminar, lo que no es compatible.</span><span class="sxs-lookup"><span data-stu-id="5080f-153">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="5080f-154">Los proyectos están basados en project.json, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="5080f-154">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="5080f-155">Para obtener más información sobre los cambios de formato de proyecto, consulte [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Información general de alto nivel sobre los cambios).</span><span class="sxs-lookup"><span data-stu-id="5080f-155">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

> [!TIP]
> <span data-ttu-id="5080f-156">Para comprobar la versión de Visual Studio 2017, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5080f-156">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="5080f-157">En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="5080f-157">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="5080f-158">En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.</span><span class="sxs-lookup"><span data-stu-id="5080f-158">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="5080f-159">Para las aplicaciones de .NET Core 2.1 Preview 1, Visual Studio 2017 versión 15.6 Preview 6 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="5080f-159">For .NET Core 2.1 Preview 1 apps, Visual Studio 2017 version 15.6 Preview 6 or higher.</span></span>
>   * <span data-ttu-id="5080f-160">Para las aplicaciones de .NET Core 2.0, debe ser Visual Studio 2017 versión 15.3 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="5080f-160">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="5080f-161">Para las aplicaciones de .NET Core 1.x, debe ser Visual Studio 2017 versión 15.0 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="5080f-161">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>

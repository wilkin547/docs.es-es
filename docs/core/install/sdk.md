---
title: 'Instalación del SDK de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para desarrollar aplicaciones en .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 0aa323533dd9136372c2bbc330c9c3056fdf428c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157576"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="609f1-104">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="609f1-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="609f1-105">En este artículo obtendrá información sobre cómo instalar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609f1-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="609f1-106">El SDK de .NET Core se usa para crear aplicaciones y bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609f1-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="609f1-107">El entorno de ejecución de .NET Core siempre se instala con el SDK.</span><span class="sxs-lookup"><span data-stu-id="609f1-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="609f1-108">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="609f1-108">Install with an installer</span></span>

<span data-ttu-id="609f1-109">Windows tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="609f1-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="609f1-110">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="609f1-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="609f1-111">CPU de x86 (32 bits)</span><span class="sxs-lookup"><span data-stu-id="609f1-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="609f1-112">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="609f1-112">Install with an installer</span></span>

<span data-ttu-id="609f1-113">macOS tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="609f1-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="609f1-114">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="609f1-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="609f1-115">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="609f1-115">Download and manually install</span></span>

<span data-ttu-id="609f1-116">Como alternativa a los instaladores de macOS para .NET Core, puede descargar e instalar el SDK de forma manual.</span><span class="sxs-lookup"><span data-stu-id="609f1-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="609f1-117">Para extraer el SDK y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609f1-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="609f1-118">Después, abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="609f1-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="609f1-119">Se supone que el entorno de ejecución se ha descargado al archivo `~/Downloads/dotnet-sdk.pkg`.</span><span class="sxs-lookup"><span data-stu-id="609f1-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="609f1-120">Instalación con un administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="609f1-120">Install with a package manager</span></span>

<span data-ttu-id="609f1-121">Se puede instalar el SDK de .NET Core con muchos de los administradores de paquetes comunes de Linux.</span><span class="sxs-lookup"><span data-stu-id="609f1-121">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="609f1-122">Para obtener más información, vea [Administrador de paquetes de Linux: instalación de .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-122">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="609f1-123">Su instalación con un administrador de paquetes solo se admite en la arquitectura x64.</span><span class="sxs-lookup"><span data-stu-id="609f1-123">Installing with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="609f1-124">Si va a instalar el SDK de .NET Core con otra arquitectura, como ARM, siga las instrucciones de [Descarga e instalación de forma manual](#download-and-manually-install) a continuación.</span><span class="sxs-lookup"><span data-stu-id="609f1-124">If you're installing the .NET Core SDK with a different architecture, such as ARM, follow the [Download and manually install](#download-and-manually-install) instructions below.</span></span> <span data-ttu-id="609f1-125">Para obtener más información sobre qué arquitecturas se admiten, consulte [Dependencias y requisitos de .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-125">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="609f1-126">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="609f1-126">Download and manually install</span></span>

<span data-ttu-id="609f1-127">Para extraer el SDK y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609f1-127">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="609f1-128">Después, abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="609f1-128">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="609f1-129">Los comandos `export` anteriores solo hacen que los comandos de la CLI de .NET Core estén disponibles para la sesión de terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="609f1-129">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="609f1-130">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="609f1-130">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="609f1-131">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="609f1-131">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="609f1-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="609f1-132">For example:</span></span>
>
> - <span data-ttu-id="609f1-133">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="609f1-133">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="609f1-134">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="609f1-134">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="609f1-135">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="609f1-135">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="609f1-136">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="609f1-136">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="609f1-137">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="609f1-137">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="609f1-138">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="609f1-138">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="609f1-139">Instalación con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="609f1-139">Install with Visual Studio</span></span>

<span data-ttu-id="609f1-140">Si usa Visual Studio para desarrollar aplicaciones de .NET Core, en la tabla siguiente se describe la versión mínima necesaria de Visual Studio, basada en la versión del SDK de .NET Core de destino.</span><span class="sxs-lookup"><span data-stu-id="609f1-140">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="609f1-141">Versión del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="609f1-141">.NET Core SDK version</span></span> | <span data-ttu-id="609f1-142">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="609f1-142">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="609f1-143">3.1</span><span class="sxs-lookup"><span data-stu-id="609f1-143">3.1</span></span>                   | <span data-ttu-id="609f1-144">Visual Studio 2019, versión 16.4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="609f1-144">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="609f1-145">3.0</span><span class="sxs-lookup"><span data-stu-id="609f1-145">3.0</span></span>                   | <span data-ttu-id="609f1-146">Visual Studio 2019, versión 16.3 o posterior.</span><span class="sxs-lookup"><span data-stu-id="609f1-146">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="609f1-147">2.2</span><span class="sxs-lookup"><span data-stu-id="609f1-147">2.2</span></span>                   | <span data-ttu-id="609f1-148">Visual Studio 2017, versión 15.9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="609f1-148">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="609f1-149">2.1</span><span class="sxs-lookup"><span data-stu-id="609f1-149">2.1</span></span>                   | <span data-ttu-id="609f1-150">Visual Studio 2017, versión 15.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="609f1-150">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="609f1-151">Si ya tiene Visual Studio instalado, puede comprobar la versión siguiendo los pasos que se detallan a continuación.</span><span class="sxs-lookup"><span data-stu-id="609f1-151">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="609f1-152">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="609f1-152">Open Visual Studio.</span></span>
01. <span data-ttu-id="609f1-153">Seleccione **Ayuda** > **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="609f1-153">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="609f1-154">Lea el número de versión en el cuadro de diálogo **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="609f1-154">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="609f1-155">Visual Studio puede instalar el SDK y el entorno de ejecución de .NET Core más recientes.</span><span class="sxs-lookup"><span data-stu-id="609f1-155">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="609f1-156">[Descargue Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="609f1-156">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="609f1-157">Selección de una carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="609f1-157">Select a workload</span></span>

<span data-ttu-id="609f1-158">Al instalar o modificar Visual Studio, seleccione una de las cargas de trabajo siguientes o más, en función del tipo de aplicación que quiera compilar:</span><span class="sxs-lookup"><span data-stu-id="609f1-158">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="609f1-159">La carga de trabajo **Desarrollo multiplataforma de .NET Core** en la sección **Otros conjuntos de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="609f1-159">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="609f1-160">La carga de trabajo **Desarrollo de ASP.NET y web** en la sección **Web y nube**.</span><span class="sxs-lookup"><span data-stu-id="609f1-160">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="609f1-161">La carga de trabajo **Desarrollo de Azure** en la sección **Web y nube**.</span><span class="sxs-lookup"><span data-stu-id="609f1-161">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="609f1-162">La carga de trabajo **Desarrollo de escritorio de .NET** en la sección **Móviles y de escritorio**.</span><span class="sxs-lookup"><span data-stu-id="609f1-162">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="609f1-163">[![Visual Studio 2019 para Windows con la carga de trabajo de .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="609f1-163">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="609f1-164">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="609f1-164">Download and manually install</span></span>

<span data-ttu-id="609f1-165">Para extraer el runtime y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="609f1-165">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="609f1-166">A continuación, cree un directorio para la instalación, por ejemplo `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="609f1-166">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="609f1-167">Por último, extraiga el archivo zip descargado en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="609f1-167">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="609f1-168">De forma predeterminada, los comandos y las aplicaciones de la CLI de .NET Core no usarán la versión de .NET Core instalada de esta manera.</span><span class="sxs-lookup"><span data-stu-id="609f1-168">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="609f1-169">Debe optar explícitamente por usarla.</span><span class="sxs-lookup"><span data-stu-id="609f1-169">You have to explicitly choose to use it.</span></span> <span data-ttu-id="609f1-170">Para ello, cambie las variables de entorno con las que se inicia una aplicación:</span><span class="sxs-lookup"><span data-stu-id="609f1-170">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="609f1-171">Este enfoque permite instalar varias versiones en ubicaciones independientes y elegir explícitamente qué ubicación de instalación debe usar una aplicación mediante la ejecución de la aplicación con variables de entorno que apuntan a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="609f1-171">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="609f1-172">Incluso cuando se establecen estas variables de entorno, .NET Core sigue teniendo en cuenta la ubicación de instalación global predeterminada al seleccionar el mejor marco para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="609f1-172">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="609f1-173">Normalmente, el valor predeterminado es `C:\Program Files\dotnet`, que usan los instaladores.</span><span class="sxs-lookup"><span data-stu-id="609f1-173">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="609f1-174">Puede indicar al motor en tiempo de ejecución que solo use la ubicación de instalación personalizada mediante la configuración de esta variable de entorno:</span><span class="sxs-lookup"><span data-stu-id="609f1-174">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="609f1-175">Instalación con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="609f1-175">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="609f1-176">Visual Studio para Mac instala el SDK de .NET Core cuando se selecciona la carga de trabajo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="609f1-176">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="609f1-177">Para empezar con el desarrollo en .NET Core en macOS, vea [Instalación de Visual Studio 2019 para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="609f1-177">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="609f1-178">Para obtener la versión más reciente, .NET Core 3.1, se debe usar la versión preliminar de Visual Studio para Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="609f1-178">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="609f1-179">[![Visual Studio 2019 para Mac de macOS con la característica de carga de trabajo de .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="609f1-179">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="609f1-180">Instalación junto con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="609f1-180">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="609f1-181">Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio.</span><span class="sxs-lookup"><span data-stu-id="609f1-181">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="609f1-182">Visual Studio Code está disponible para Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="609f1-182">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="609f1-183">Aunque Visual Studio Code no viene con un instalador automatizado de .NET Core como Visual Studio, agregar compatibilidad con .NET Core es sencillo.</span><span class="sxs-lookup"><span data-stu-id="609f1-183">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="609f1-184">[Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="609f1-184">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="609f1-185">[Descargue e instale el SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="609f1-185">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="609f1-186">[Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="609f1-186">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="609f1-187">Instalación mediante la automatización de PowerShell</span><span class="sxs-lookup"><span data-stu-id="609f1-187">Install with PowerShell automation</span></span>

<span data-ttu-id="609f1-188">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del SDK.</span><span class="sxs-lookup"><span data-stu-id="609f1-188">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="609f1-189">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-189">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="609f1-190">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="609f1-190">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="609f1-191">Para instalar la versión actual de .NET Core, ejecute el script con el modificador siguiente.</span><span class="sxs-lookup"><span data-stu-id="609f1-191">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="609f1-192">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="609f1-192">Install with bash automation</span></span>

<span data-ttu-id="609f1-193">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del SDK.</span><span class="sxs-lookup"><span data-stu-id="609f1-193">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="609f1-194">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-194">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="609f1-195">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="609f1-195">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="609f1-196">Para instalar la versión actual de .NET Core, ejecute el script con el modificador siguiente.</span><span class="sxs-lookup"><span data-stu-id="609f1-196">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="609f1-197">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="609f1-197">All .NET Core downloads</span></span>

<span data-ttu-id="609f1-198">Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="609f1-198">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="609f1-199">Descargas de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="609f1-199">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="609f1-200">Descargas de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="609f1-200">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="609f1-201">Descargas de .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="609f1-201">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="609f1-202">Descargas de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="609f1-202">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="609f1-203">Docker</span><span class="sxs-lookup"><span data-stu-id="609f1-203">Docker</span></span>

<span data-ttu-id="609f1-204">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="609f1-204">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="609f1-205">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="609f1-205">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="609f1-206">.NET Core puede ejecutarse en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="609f1-206">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="609f1-207">Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="609f1-207">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="609f1-208">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="609f1-208">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="609f1-209">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="609f1-209">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="609f1-210">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="609f1-210">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="609f1-211">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-211">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="609f1-212">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="609f1-212">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="609f1-213">[Tutorial: Tutorial Hola mundo](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-213">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="609f1-214">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-214">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="609f1-215">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-215">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="609f1-216">[Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-216">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="609f1-217">[Tutorial: Introducción a macOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-217">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="609f1-218">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-218">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="609f1-219">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-219">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="609f1-220">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-220">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="609f1-221">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="609f1-221">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

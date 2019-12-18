---
title: 'Instalación del SDK de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para desarrollar aplicaciones en .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1f7efaedaa1a0be90f7b619f954bdf78eecafa07
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74999066"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="867f2-104">Instalación del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="867f2-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="867f2-105">En este artículo obtendrá información sobre cómo instalar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="867f2-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="867f2-106">El SDK de .NET Core se usa para crear aplicaciones y bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="867f2-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="867f2-107">El entorno de ejecución de .NET Core siempre se instala con el SDK.</span><span class="sxs-lookup"><span data-stu-id="867f2-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="867f2-108">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="867f2-108">Install with an installer</span></span>

<span data-ttu-id="867f2-109">Windows tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="867f2-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="867f2-110">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="867f2-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="867f2-111">CPU de x86 (32 bits)</span><span class="sxs-lookup"><span data-stu-id="867f2-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="867f2-112">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="867f2-112">Install with an installer</span></span>

<span data-ttu-id="867f2-113">macOS tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="867f2-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="867f2-114">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="867f2-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="867f2-115">Instalación con un administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="867f2-115">Install with a package manager</span></span>

<span data-ttu-id="867f2-116">Se puede instalar el SDK de .NET Core con muchos de los administradores de paquetes comunes de Linux.</span><span class="sxs-lookup"><span data-stu-id="867f2-116">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="867f2-117">Para obtener más información, vea [Administrador de paquetes de Linux: instalación de .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-117">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="867f2-118">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="867f2-118">Download and manually install</span></span>

<span data-ttu-id="867f2-119">Para extraer el SDK y hacer que los comandos estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="867f2-119">To extract the SDK and make the commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="867f2-120">Después, abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="867f2-120">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="867f2-121">Los comandos anteriores solo harán que los comandos del SDK de .NET estén disponibles para la sesión de terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="867f2-121">The above commands will only make the .NET SDK commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="867f2-122">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="867f2-122">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="867f2-123">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="867f2-123">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="867f2-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="867f2-124">For example:</span></span>
>
> - <span data-ttu-id="867f2-125">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="867f2-125">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="867f2-126">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="867f2-126">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="867f2-127">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="867f2-127">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="867f2-128">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="867f2-128">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="867f2-129">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="867f2-129">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="867f2-130">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="867f2-130">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="867f2-131">Instalación con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="867f2-131">Install with Visual Studio</span></span>

<span data-ttu-id="867f2-132">Si usa Visual Studio para desarrollar aplicaciones de .NET Core, en la tabla siguiente se describe la versión mínima necesaria de Visual Studio, basada en la versión del SDK de .NET Core de destino.</span><span class="sxs-lookup"><span data-stu-id="867f2-132">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="867f2-133">Versión del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="867f2-133">.NET Core SDK version</span></span> | <span data-ttu-id="867f2-134">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="867f2-134">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="867f2-135">3.1</span><span class="sxs-lookup"><span data-stu-id="867f2-135">3.1</span></span>                   | <span data-ttu-id="867f2-136">Visual Studio 2019, versión 16.4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="867f2-136">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="867f2-137">3.0</span><span class="sxs-lookup"><span data-stu-id="867f2-137">3.0</span></span>                   | <span data-ttu-id="867f2-138">Visual Studio 2019, versión 16.3 o posterior.</span><span class="sxs-lookup"><span data-stu-id="867f2-138">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="867f2-139">2.2</span><span class="sxs-lookup"><span data-stu-id="867f2-139">2.2</span></span>                   | <span data-ttu-id="867f2-140">Visual Studio 2017, versión 15.9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="867f2-140">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="867f2-141">2.1</span><span class="sxs-lookup"><span data-stu-id="867f2-141">2.1</span></span>                   | <span data-ttu-id="867f2-142">Visual Studio 2017, versión 15.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="867f2-142">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="867f2-143">Si ya tiene Visual Studio instalado, puede comprobar la versión siguiendo los pasos que se detallan a continuación.</span><span class="sxs-lookup"><span data-stu-id="867f2-143">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="867f2-144">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="867f2-144">Open Visual Studio.</span></span>
01. <span data-ttu-id="867f2-145">Seleccione **Ayuda** > **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="867f2-145">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="867f2-146">Lea el número de versión en el cuadro de diálogo **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="867f2-146">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="867f2-147">Visual Studio puede instalar el SDK y el entorno de ejecución de .NET Core más recientes.</span><span class="sxs-lookup"><span data-stu-id="867f2-147">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="867f2-148">[Descargue Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="867f2-148">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="867f2-149">Selección de una carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="867f2-149">Select a workload</span></span>

<span data-ttu-id="867f2-150">Al instalar o modificar Visual Studio, seleccione una de las cargas de trabajo siguientes, en función del tipo de aplicación que quiera compilar:</span><span class="sxs-lookup"><span data-stu-id="867f2-150">When installing or modifying Visual Studio, select one of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="867f2-151">La carga de trabajo **Desarrollo multiplataforma de .NET Core** en la sección **Otros conjuntos de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="867f2-151">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="867f2-152">La carga de trabajo **Desarrollo de ASP.NET y web** en la sección **Web y nube**.</span><span class="sxs-lookup"><span data-stu-id="867f2-152">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="867f2-153">La carga de trabajo **Desarrollo de Azure** en la sección **Web y nube**.</span><span class="sxs-lookup"><span data-stu-id="867f2-153">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="867f2-154">La carga de trabajo **Desarrollo de escritorio de .NET** en la sección **Móviles y de escritorio**.</span><span class="sxs-lookup"><span data-stu-id="867f2-154">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="867f2-155">[![Visual Studio 2019 para Windows con la carga de trabajo de .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="867f2-155">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="867f2-156">Instalación con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="867f2-156">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="867f2-157">Visual Studio para Mac instala el SDK de .NET Core cuando se selecciona la carga de trabajo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="867f2-157">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="867f2-158">Para empezar con el desarrollo en .NET Core en macOS, vea [Instalación de Visual Studio 2019 para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="867f2-158">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="867f2-159">Para obtener la versión más reciente, .NET Core 3.1, se debe usar la versión preliminar de Visual Studio para Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="867f2-159">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="867f2-160">[![Visual Studio 2019 para Mac de macOS con la característica de carga de trabajo de .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="867f2-160">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="867f2-161">Instalación junto con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="867f2-161">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="867f2-162">Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio.</span><span class="sxs-lookup"><span data-stu-id="867f2-162">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="867f2-163">Visual Studio Code está disponible para Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="867f2-163">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="867f2-164">Aunque Visual Studio Code no viene con un instalador automatizado de .NET Core como Visual Studio, agregar compatibilidad con .NET Core es sencillo.</span><span class="sxs-lookup"><span data-stu-id="867f2-164">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="867f2-165">[Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="867f2-165">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="867f2-166">[Descargue e instale el SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="867f2-166">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="867f2-167">[Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="867f2-167">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="867f2-168">Instalación mediante la automatización de PowerShell</span><span class="sxs-lookup"><span data-stu-id="867f2-168">Install with PowerShell automation</span></span>

<span data-ttu-id="867f2-169">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del SDK.</span><span class="sxs-lookup"><span data-stu-id="867f2-169">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="867f2-170">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-170">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="867f2-171">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="867f2-171">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="867f2-172">Para instalar la versión actual de .NET Core, ejecute el script con el modificador siguiente.</span><span class="sxs-lookup"><span data-stu-id="867f2-172">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="867f2-173">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="867f2-173">Install with bash automation</span></span>

<span data-ttu-id="867f2-174">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del SDK.</span><span class="sxs-lookup"><span data-stu-id="867f2-174">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="867f2-175">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-175">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="867f2-176">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="867f2-176">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="867f2-177">Para instalar la versión actual de .NET Core, ejecute el script con el modificador siguiente.</span><span class="sxs-lookup"><span data-stu-id="867f2-177">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="867f2-178">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="867f2-178">All .NET Core downloads</span></span>

<span data-ttu-id="867f2-179">Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="867f2-179">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="867f2-180">Descargas de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="867f2-180">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="867f2-181">Descargas de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="867f2-181">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="867f2-182">Descargas de .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="867f2-182">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="867f2-183">Descargas de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="867f2-183">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="867f2-184">Docker</span><span class="sxs-lookup"><span data-stu-id="867f2-184">Docker</span></span>

<span data-ttu-id="867f2-185">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="867f2-185">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="867f2-186">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="867f2-186">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="867f2-187">.NET Core puede ejecutarse en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="867f2-187">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="867f2-188">Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="867f2-188">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="867f2-189">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="867f2-189">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="867f2-190">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="867f2-190">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="867f2-191">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="867f2-191">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="867f2-192">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-192">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="867f2-193">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="867f2-193">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="867f2-194">[Tutorial: Tutorial Hola mundo de C#](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-194">[Tutorial: C# Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="867f2-195">[Tutorial: Tutorial Hola mundo de Visual Basic](../tutorials/vb-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-195">[Tutorial: Visual Basic Hello World tutorial](../tutorials/vb-with-visual-studio.md).</span></span>
- <span data-ttu-id="867f2-196">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-196">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="867f2-197">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-197">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="867f2-198">[Tutorial: Introducción a macOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-198">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="867f2-199">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-199">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="867f2-200">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-200">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="867f2-201">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="867f2-202">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="867f2-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

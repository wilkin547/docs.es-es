---
title: 'Instalación manual de .NET en Linux: .NET'
description: Muestra cómo instalar el SDK y el entorno de ejecución de .NET sin un administrador de paquetes en Linux. Use el script de instalación o extraiga manualmente los archivos binarios.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 414246e472c3d58a6768311bd7a4635100f3b618
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105185"
---
# <a name="install-the-net-sdk-or-the-net-runtime-manually"></a><span data-ttu-id="8ac09-104">Instalación manual del SDK y el entorno de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="8ac09-104">Install the .NET SDK or the .NET Runtime manually</span></span>

<span data-ttu-id="8ac09-105">.NET es compatible con Linux. En este artículo se describe cómo instalar .NET en Linux mediante el script de instalación o la extracción de los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="8ac09-105">.NET is supported on Linux and this article describes how to install .NET on Linux using the install script or by extracting the binaries.</span></span> <span data-ttu-id="8ac09-106">Para obtener una lista de las distribuciones que admiten el administrador de paquetes integrado, consulte [Instalación de .NET en Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="8ac09-106">For a list of distributions that support the built-in package manager, see [Install .NET on Linux](linux.md).</span></span>

<span data-ttu-id="8ac09-107">También puede instalar .NET con un snap.</span><span class="sxs-lookup"><span data-stu-id="8ac09-107">You can also install .NET with snap.</span></span> <span data-ttu-id="8ac09-108">Para obtener más información, consulte [Instalación del SDK y el entorno de ejecución de .NET con un snap](linux-snap.md).</span><span class="sxs-lookup"><span data-stu-id="8ac09-108">For more information, see [Install the .NET SDK or the .NET Runtime with Snap](linux-snap.md).</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="net-releases"></a><span data-ttu-id="8ac09-109">Versiones de .NET</span><span class="sxs-lookup"><span data-stu-id="8ac09-109">.NET releases</span></span>

<span data-ttu-id="8ac09-110">En la tabla siguiente se enumeran las versiones de .NET (y .NET Core):</span><span class="sxs-lookup"><span data-stu-id="8ac09-110">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="8ac09-111">✔️ Admitida</span><span class="sxs-lookup"><span data-stu-id="8ac09-111">✔️ Supported</span></span> | <span data-ttu-id="8ac09-112">❌ No admitida</span><span class="sxs-lookup"><span data-stu-id="8ac09-112">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="8ac09-113">5.0</span><span class="sxs-lookup"><span data-stu-id="8ac09-113">5.0</span></span>         | <span data-ttu-id="8ac09-114">3.0</span><span class="sxs-lookup"><span data-stu-id="8ac09-114">3.0</span></span>           |
| <span data-ttu-id="8ac09-115">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="8ac09-115">3.1 (LTS)</span></span>   | <span data-ttu-id="8ac09-116">2.2</span><span class="sxs-lookup"><span data-stu-id="8ac09-116">2.2</span></span>           |
| <span data-ttu-id="8ac09-117">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="8ac09-117">2.1 (LTS)</span></span>   | <span data-ttu-id="8ac09-118">2,0</span><span class="sxs-lookup"><span data-stu-id="8ac09-118">2.0</span></span>           |
|             | <span data-ttu-id="8ac09-119">1,1</span><span class="sxs-lookup"><span data-stu-id="8ac09-119">1.1</span></span>           |
|             | <span data-ttu-id="8ac09-120">1,0</span><span class="sxs-lookup"><span data-stu-id="8ac09-120">1.0</span></span>           |

<span data-ttu-id="8ac09-121">Para obtener más información sobre el ciclo de vida de las versiones de .NET, consulte la [directiva de compatibilidad de .NET Core y .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="8ac09-121">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="dependencies"></a><span data-ttu-id="8ac09-122">Dependencias</span><span class="sxs-lookup"><span data-stu-id="8ac09-122">Dependencies</span></span>

<span data-ttu-id="8ac09-123">Al instalar .NET, es posible que las dependencias específicas no estén instaladas, como cuando se realiza la [instalación manual](#manual-install).</span><span class="sxs-lookup"><span data-stu-id="8ac09-123">It's possible that when you install .NET, specific dependencies may not be installed, such as when [manually installing](#manual-install).</span></span> <span data-ttu-id="8ac09-124">En la lista siguiente se detallan las distribuciones de Linux que son compatibles con Microsoft y que contienen dependencias que es posible que deba instalar.</span><span class="sxs-lookup"><span data-stu-id="8ac09-124">The following list details Linux distributions that are supported by Microsoft and have dependencies you may need to install.</span></span> <span data-ttu-id="8ac09-125">Consulte la página de la distribución para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="8ac09-125">Check the distribution page for more information:</span></span>

- [<span data-ttu-id="8ac09-126">Alpine</span><span class="sxs-lookup"><span data-stu-id="8ac09-126">Alpine</span></span>](linux-alpine.md#dependencies)
- [<span data-ttu-id="8ac09-127">Debian</span><span class="sxs-lookup"><span data-stu-id="8ac09-127">Debian</span></span>](linux-debian.md#dependencies)
- [<span data-ttu-id="8ac09-128">CentOS</span><span class="sxs-lookup"><span data-stu-id="8ac09-128">CentOS</span></span>](linux-centos.md#dependencies)
- [<span data-ttu-id="8ac09-129">Fedora</span><span class="sxs-lookup"><span data-stu-id="8ac09-129">Fedora</span></span>](linux-fedora.md#dependencies)
- [<span data-ttu-id="8ac09-130">RHEL</span><span class="sxs-lookup"><span data-stu-id="8ac09-130">RHEL</span></span>](linux-rhel.md#dependencies)
- [<span data-ttu-id="8ac09-131">SLES</span><span class="sxs-lookup"><span data-stu-id="8ac09-131">SLES</span></span>](linux-sles.md#dependencies)
- [<span data-ttu-id="8ac09-132">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="8ac09-132">Ubuntu</span></span>](linux-ubuntu.md#dependencies)

<span data-ttu-id="8ac09-133">Para obtener información genérica sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="8ac09-133">For generic information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

### <a name="rpm-dependencies"></a><span data-ttu-id="8ac09-134">Dependencias de RPM</span><span class="sxs-lookup"><span data-stu-id="8ac09-134">RPM dependencies</span></span>

<span data-ttu-id="8ac09-135">Si su distribución no aparece en la lista anterior y se basa en RPM, puede que necesite las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="8ac09-135">If your distribution wasn't previously listed, and is RPM-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="8ac09-136">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="8ac09-136">krb5-libs</span></span>
- <span data-ttu-id="8ac09-137">libicu</span><span class="sxs-lookup"><span data-stu-id="8ac09-137">libicu</span></span>
- <span data-ttu-id="8ac09-138">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="8ac09-138">openssl-libs</span></span>

<span data-ttu-id="8ac09-139">Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="8ac09-139">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

### <a name="deb-dependencies"></a><span data-ttu-id="8ac09-140">Dependencias de DEB</span><span class="sxs-lookup"><span data-stu-id="8ac09-140">DEB dependencies</span></span>

<span data-ttu-id="8ac09-141">Si su distribución no aparece en la lista anterior y se basa en Debian, puede que necesite las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="8ac09-141">If your distribution wasn't previously listed, and is debian-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="8ac09-142">libc6</span><span class="sxs-lookup"><span data-stu-id="8ac09-142">libc6</span></span>
- <span data-ttu-id="8ac09-143">libgcc1</span><span class="sxs-lookup"><span data-stu-id="8ac09-143">libgcc1</span></span>
- <span data-ttu-id="8ac09-144">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="8ac09-144">libgssapi-krb5-2</span></span>
- <span data-ttu-id="8ac09-145">libicu67</span><span class="sxs-lookup"><span data-stu-id="8ac09-145">libicu67</span></span>
- <span data-ttu-id="8ac09-146">libssl1.1</span><span class="sxs-lookup"><span data-stu-id="8ac09-146">libssl1.1</span></span>
- <span data-ttu-id="8ac09-147">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="8ac09-147">libstdc++6</span></span>
- <span data-ttu-id="8ac09-148">zlib1g</span><span class="sxs-lookup"><span data-stu-id="8ac09-148">zlib1g</span></span>

### <a name="common-dependencies"></a><span data-ttu-id="8ac09-149">Dependencias comunes</span><span class="sxs-lookup"><span data-stu-id="8ac09-149">Common dependencies</span></span>

<span data-ttu-id="8ac09-150">En el caso de las aplicaciones de .NET en las que se usa el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ac09-150">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="8ac09-151">libgdiplus (versión 6.0.1 o posterior)</span><span class="sxs-lookup"><span data-stu-id="8ac09-151">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="8ac09-152">Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="8ac09-152">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="8ac09-153">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="8ac09-153">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="8ac09-154">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="8ac09-154">Scripted install</span></span>

<span data-ttu-id="8ac09-155">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del **SDK** y del **Runtime**.</span><span class="sxs-lookup"><span data-stu-id="8ac09-155">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="8ac09-156">Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="8ac09-156">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="8ac09-157">El valor predeterminado del script es instalar la versión más reciente del SDK de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="8ac09-157">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="8ac09-158">Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="8ac09-158">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="8ac09-159">Para instalar el entorno de ejecución de .NET en lugar del SDK, use el parámetro `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="8ac09-159">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="8ac09-160">Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica.</span><span class="sxs-lookup"><span data-stu-id="8ac09-160">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="8ac09-161">El comando siguiente instala el SDK de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="8ac09-161">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="8ac09-162">Para más información, consulte la [referencia de los scripts de dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="8ac09-162">For more information, see [dotnet-install scripts reference](../tools/dotnet-install-script.md).</span></span>

## <a name="manual-install"></a><span data-ttu-id="8ac09-163">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="8ac09-163">Manual install</span></span>

<!-- Note, this content is copied in macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="8ac09-164">Como alternativa a los administradores de paquetes, puede descargar e instalar manualmente el SDK y el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ac09-164">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="8ac09-165">La instalación manual se suele usar como parte de las pruebas de integración continua o en distribuciones de Linux no admitidas.</span><span class="sxs-lookup"><span data-stu-id="8ac09-165">Manual install is commonly used as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="8ac09-166">Para un desarrollador o usuario, es mejor usar un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8ac09-166">For a developer or user, it's better to use a package manager.</span></span>

<span data-ttu-id="8ac09-167">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8ac09-167">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="8ac09-168">En primer lugar, descargue una versión **binaria** del SDK o del entorno de ejecución de uno de los siguientes sitios:</span><span class="sxs-lookup"><span data-stu-id="8ac09-168">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="8ac09-169">✔️ [Descargas de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="8ac09-169">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="8ac09-170">✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet/3.1)</span><span class="sxs-lookup"><span data-stu-id="8ac09-170">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet/3.1)</span></span>
- <span data-ttu-id="8ac09-171">✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet/2.1)</span><span class="sxs-lookup"><span data-stu-id="8ac09-171">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet/2.1)</span></span>
- [<span data-ttu-id="8ac09-172">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="8ac09-172">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet)

<span data-ttu-id="8ac09-173">A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET. Luego, asegúrese de que .NET esté en PATH.</span><span class="sxs-lookup"><span data-stu-id="8ac09-173">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="8ac09-174">Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET.</span><span class="sxs-lookup"><span data-stu-id="8ac09-174">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="8ac09-175">Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo.</span><span class="sxs-lookup"><span data-stu-id="8ac09-175">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="8ac09-176">El nombre del archivo puede ser distinto en función de lo que haya descargado.</span><span class="sxs-lookup"><span data-stu-id="8ac09-176">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="8ac09-177">**Use los siguientes comandos para extraer el entorno de ejecución o el SDK que descargó**.</span><span class="sxs-lookup"><span data-stu-id="8ac09-177">**Use the following commands to extract the runtime or SDK that you downloaded.**</span></span> <span data-ttu-id="8ac09-178">Recuerde cambiar el valor de `DOTNET_FILE` por el nombre del archivo:</span><span class="sxs-lookup"><span data-stu-id="8ac09-178">Remember to change the `DOTNET_FILE` value to your file name:</span></span>

```bash
DOTNET_FILE=dotnet-sdk-5.0.102-linux-x64.tar.gz
export DOTNET_ROOT=$HOME/dotnet

mkdir -p "$DOTNET_ROOT" && tar zxf "$DOTNET_FILE" -C "$DOTNET_ROOT"

export PATH=$PATH:$DOTNET_ROOT
```

> [!TIP]
> <span data-ttu-id="8ac09-179">Los comandos `export` anteriores solo hacen que los de la CLI de .NET estén disponibles para la sesión del terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="8ac09-179">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="8ac09-180">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="8ac09-180">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="8ac09-181">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="8ac09-181">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="8ac09-182">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8ac09-182">For example:</span></span>
>
> - <span data-ttu-id="8ac09-183">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="8ac09-183">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="8ac09-184">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="8ac09-184">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="8ac09-185">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="8ac09-185">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="8ac09-186">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="8ac09-186">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="8ac09-187">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="8ac09-187">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="8ac09-188">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="8ac09-188">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="8ac09-189">Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ac09-189">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ac09-190">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ac09-190">Next steps</span></span>

- [<span data-ttu-id="8ac09-191">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="8ac09-191">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="8ac09-192">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8ac09-192">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)

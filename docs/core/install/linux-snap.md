---
title: 'Instalación de .NET en Linux con un snap: .NET'
description: Muestra cómo instalar el SDK o el entorno de ejecución de .NET en Linux con un snap.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 0d91f5049c92df240e2c3e26bc67952abe17fedc
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190104"
---
# <a name="install-the-net-sdk-or-the-net-runtime-with-snap"></a><span data-ttu-id="58bc8-103">Instalación del SDK y el entorno de ejecución de .NET con un snap</span><span class="sxs-lookup"><span data-stu-id="58bc8-103">Install the .NET SDK or the .NET Runtime with Snap</span></span>

<span data-ttu-id="58bc8-104">Use un paquete de snaps para instalar el SDK o el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="58bc8-104">Use a Snap package to install the .NET SDK or .NET Runtime.</span></span> <span data-ttu-id="58bc8-105">Los snaps son una excelente alternativa para el administrador de paquetes integrada en la distribución de Linux.</span><span class="sxs-lookup"><span data-stu-id="58bc8-105">Snaps are a great alternative to the package manager built into your Linux distribution.</span></span> <span data-ttu-id="58bc8-106">En este artículo se describe cómo instalar .NET mediante un [snap](https://snapcraft.io/dotnet-sdk).</span><span class="sxs-lookup"><span data-stu-id="58bc8-106">This article describes how to install .NET through [Snap](https://snapcraft.io/dotnet-sdk).</span></span>

<span data-ttu-id="58bc8-107">Un snap es una agrupación de una aplicación y sus dependencias que funcionan sin modificaciones en muchas distribuciones de Linux diferentes.</span><span class="sxs-lookup"><span data-stu-id="58bc8-107">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="58bc8-108">Los snaps se reconocen y se instalan desde el almacén de snaps.</span><span class="sxs-lookup"><span data-stu-id="58bc8-108">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="58bc8-109">Para más información sobre Snap, consulte [Introducción a Snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="58bc8-109">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

> [!CAUTION]
> <span data-ttu-id="58bc8-110">Los paquetes de snaps no se admiten en WSL2 en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="58bc8-110">Snap packages aren't supported in WSL2 on Windows 10.</span></span> <span data-ttu-id="58bc8-111">Como alternativa, use el [script `dotnet-install`](linux-scripted-manual.md#scripted-install) o el administrador de paquetes para la distribución de WSL2 determinada.</span><span class="sxs-lookup"><span data-stu-id="58bc8-111">As an alternative, use the [`dotnet-install` script](linux-scripted-manual.md#scripted-install) or the package manager for the particular WSL2 distribution.</span></span> <span data-ttu-id="58bc8-112">No se recomienda, pero puede intentar habilitar los snaps con una [solución no admitida de los foros de snapcraft](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033).</span><span class="sxs-lookup"><span data-stu-id="58bc8-112">It's not recommended but you can try to enable snap with an [unsupported workaround from the snapcraft forums](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033).</span></span>

## <a name="net-releases"></a><span data-ttu-id="58bc8-113">Versiones de .NET</span><span class="sxs-lookup"><span data-stu-id="58bc8-113">.NET releases</span></span>

<span data-ttu-id="58bc8-114">Solo las versiones admitidas ✔️ del SDK de .NET están disponibles mediante snaps.</span><span class="sxs-lookup"><span data-stu-id="58bc8-114">Only ✔️ supported versions of .NET SDK are available through Snap.</span></span> <span data-ttu-id="58bc8-115">Todas las versiones del entorno de ejecución de .NET están disponibles mediante snaps a partir de la versión 2.1.</span><span class="sxs-lookup"><span data-stu-id="58bc8-115">All versions of the .NET Runtime are available through snap starting with version 2.1.</span></span> <span data-ttu-id="58bc8-116">En la tabla siguiente se enumeran las versiones de .NET (y .NET Core):</span><span class="sxs-lookup"><span data-stu-id="58bc8-116">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="58bc8-117">✔️ Admitida</span><span class="sxs-lookup"><span data-stu-id="58bc8-117">✔️ Supported</span></span> | <span data-ttu-id="58bc8-118">❌ No admitida</span><span class="sxs-lookup"><span data-stu-id="58bc8-118">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="58bc8-119">5.0</span><span class="sxs-lookup"><span data-stu-id="58bc8-119">5.0</span></span>         | <span data-ttu-id="58bc8-120">3.0</span><span class="sxs-lookup"><span data-stu-id="58bc8-120">3.0</span></span>           |
| <span data-ttu-id="58bc8-121">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="58bc8-121">3.1 (LTS)</span></span>   | <span data-ttu-id="58bc8-122">2.2</span><span class="sxs-lookup"><span data-stu-id="58bc8-122">2.2</span></span>           |
| <span data-ttu-id="58bc8-123">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="58bc8-123">2.1 (LTS)</span></span>   | <span data-ttu-id="58bc8-124">2,0</span><span class="sxs-lookup"><span data-stu-id="58bc8-124">2.0</span></span>           |
|             | <span data-ttu-id="58bc8-125">1,1</span><span class="sxs-lookup"><span data-stu-id="58bc8-125">1.1</span></span>           |
|             | <span data-ttu-id="58bc8-126">1,0</span><span class="sxs-lookup"><span data-stu-id="58bc8-126">1.0</span></span>           |

<span data-ttu-id="58bc8-127">Para obtener más información sobre el ciclo de vida de las versiones de .NET, consulte la [directiva de compatibilidad de .NET Core y .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="58bc8-127">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="sdk-or-runtime"></a><span data-ttu-id="58bc8-128">SDK o entorno de ejecución</span><span class="sxs-lookup"><span data-stu-id="58bc8-128">SDK or Runtime</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install-the-sdk"></a><span data-ttu-id="58bc8-129">Instalar el SDK</span><span class="sxs-lookup"><span data-stu-id="58bc8-129">Install the SDK</span></span>

<span data-ttu-id="58bc8-130">Los paquetes de snaps para el SDK de .NET se publican con el mismo identificador: `dotnet-sdk`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-130">Snap packages for the .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="58bc8-131">Se puede instalar una versión específica del SDK mediante la especificación del canal.</span><span class="sxs-lookup"><span data-stu-id="58bc8-131">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="58bc8-132">El SDK incluye el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="58bc8-132">The SDK includes the corresponding runtime.</span></span> <span data-ttu-id="58bc8-133">En la tabla siguiente se enumeran los canales:</span><span class="sxs-lookup"><span data-stu-id="58bc8-133">The following table lists the channels:</span></span>

| <span data-ttu-id="58bc8-134">Versión de .NET</span><span class="sxs-lookup"><span data-stu-id="58bc8-134">.NET version</span></span> | <span data-ttu-id="58bc8-135">Canal o paquete de snaps</span><span class="sxs-lookup"><span data-stu-id="58bc8-135">Snap package or channel</span></span>  |
|--------------|--------------------------|
| <span data-ttu-id="58bc8-136">5.0</span><span class="sxs-lookup"><span data-stu-id="58bc8-136">5.0</span></span>          | <span data-ttu-id="58bc8-137">`5.0` o `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="58bc8-137">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="58bc8-138">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="58bc8-138">3.1 (LTS)</span></span>    | <span data-ttu-id="58bc8-139">`3.1` o `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="58bc8-139">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="58bc8-140">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="58bc8-140">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="58bc8-141">Use el comando `snap install` para instalar un paquete Snap del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="58bc8-141">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="58bc8-142">Use el parámetro `--channel` para indicar qué versión se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="58bc8-142">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="58bc8-143">Si se omite este parámetro, se usa `latest/stable`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-143">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="58bc8-144">En este ejemplo, se especifica `5.0`:</span><span class="sxs-lookup"><span data-stu-id="58bc8-144">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="58bc8-145">A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="58bc8-145">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="58bc8-146">Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-146">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="58bc8-147">Puede elegir cualquier nombre de `{alias}` que prefiera.</span><span class="sxs-lookup"><span data-stu-id="58bc8-147">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="58bc8-148">Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-148">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="58bc8-149">Cuando use el comando `dotnet50`, invocará esta versión específica de .NET.</span><span class="sxs-lookup"><span data-stu-id="58bc8-149">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="58bc8-150">Aun así, elegir un alias diferente no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que se use un comando `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-150">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be used.</span></span>

## <a name="install-the-runtime"></a><span data-ttu-id="58bc8-151">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="58bc8-151">Install the runtime</span></span>

<span data-ttu-id="58bc8-152">Los paquetes de snaps para el entorno de ejecución de .NET se publican con su propio identificador de paquete.</span><span class="sxs-lookup"><span data-stu-id="58bc8-152">Snap packages for the .NET Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="58bc8-153">En la tabla siguiente se muestra una lista de los identificadores de paquete:</span><span class="sxs-lookup"><span data-stu-id="58bc8-153">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="58bc8-154">Versión de .NET</span><span class="sxs-lookup"><span data-stu-id="58bc8-154">.NET version</span></span>      | <span data-ttu-id="58bc8-155">Paquete Snap</span><span class="sxs-lookup"><span data-stu-id="58bc8-155">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="58bc8-156">5.0</span><span class="sxs-lookup"><span data-stu-id="58bc8-156">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="58bc8-157">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="58bc8-157">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="58bc8-158">3.0</span><span class="sxs-lookup"><span data-stu-id="58bc8-158">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="58bc8-159">2.2</span><span class="sxs-lookup"><span data-stu-id="58bc8-159">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="58bc8-160">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="58bc8-160">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="58bc8-161">Use el comando `snap install` para instalar un paquete Snap del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="58bc8-161">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="58bc8-162">En este ejemplo, se instala .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="58bc8-162">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="58bc8-163">A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="58bc8-163">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="58bc8-164">El comando tiene el formato `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-164">The command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="58bc8-165">Puede elegir cualquier nombre de `{alias}` que prefiera.</span><span class="sxs-lookup"><span data-stu-id="58bc8-165">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="58bc8-166">Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-166">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="58bc8-167">Cuando use el comando `dotnet50`, invocará una versión específica de .NET.</span><span class="sxs-lookup"><span data-stu-id="58bc8-167">When you use the command `dotnet50`, you'll invoke a specific version of .NET.</span></span> <span data-ttu-id="58bc8-168">Aun así, elegir un alias diferente no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-168">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

## <a name="export-the-install-location"></a><span data-ttu-id="58bc8-169">Exportación de la ubicación de instalación</span><span class="sxs-lookup"><span data-stu-id="58bc8-169">Export the install location</span></span>

<span data-ttu-id="58bc8-170">Las herramientas suelen usar la variable de entorno `DOTNET_ROOT` para determinar dónde está instalado .NET.</span><span class="sxs-lookup"><span data-stu-id="58bc8-170">The `DOTNET_ROOT` environment variable is often used by tools to determine where .NET is installed.</span></span> <span data-ttu-id="58bc8-171">Cuando .NET se instala mediante Snap, esta variable de entorno no está configurada.</span><span class="sxs-lookup"><span data-stu-id="58bc8-171">When .NET is installed through Snap, this environment variable isn't configured.</span></span> <span data-ttu-id="58bc8-172">Debe configurar la variable de entorno *DOTNET_ROOT* en el perfil.</span><span class="sxs-lookup"><span data-stu-id="58bc8-172">You should configure the *DOTNET_ROOT* environment variable in your profile.</span></span> <span data-ttu-id="58bc8-173">La ruta a Snap usa el siguiente formato: `/snap/{package}/current`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-173">The path to the snap uses the following format: `/snap/{package}/current`.</span></span> <span data-ttu-id="58bc8-174">Por ejemplo, si ha instalado el ajuste `dotnet-sdk`, use el comando siguiente para establecer la variable de entorno en la ubicación de .NET:</span><span class="sxs-lookup"><span data-stu-id="58bc8-174">For example, if you installed the `dotnet-sdk` snap, use the following command to set the environment variable to where .NET is located:</span></span>

```bash
export DOTNET_ROOT=/snap/dotnet-sdk/current
```

> [!TIP]
> <span data-ttu-id="58bc8-175">El comando `export` anterior solo establece la variable de entorno para la sesión de terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="58bc8-175">The preceding `export` command only sets the environment variable for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="58bc8-176">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="58bc8-176">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="58bc8-177">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="58bc8-177">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="58bc8-178">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="58bc8-178">For example:</span></span>
>
> - <span data-ttu-id="58bc8-179">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="58bc8-179">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="58bc8-180">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="58bc8-180">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="58bc8-181">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="58bc8-181">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="58bc8-182">Edite el archivo de código fuente adecuado para el shell y agregue `export DOTNET_ROOT=/snap/dotnet-sdk/current`.</span><span class="sxs-lookup"><span data-stu-id="58bc8-182">Edit the appropriate source file for your shell and add `export DOTNET_ROOT=/snap/dotnet-sdk/current`.</span></span>

## <a name="tlsssl-certificate-errors"></a><span data-ttu-id="58bc8-183">Errores de certificado TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="58bc8-183">TLS/SSL Certificate errors</span></span>

<span data-ttu-id="58bc8-184">Cuando .NET se instala mediante snaps, es posible que en algunas distribuciones no se encuentren los certificados TLS/SSL de .NET y que reciba un error durante la acción `restore`:</span><span class="sxs-lookup"><span data-stu-id="58bc8-184">When .NET is installed through Snap, it's possible that on some distros the .NET TLS/SSL certificates may not be found and you may receive an error during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="58bc8-185">Para resolver este problema, establezca algunas variables de entorno:</span><span class="sxs-lookup"><span data-stu-id="58bc8-185">To resolve this problem, set a few environment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="58bc8-186">La ubicación del certificado variará en función de la distribución.</span><span class="sxs-lookup"><span data-stu-id="58bc8-186">The certificate location will vary by distro.</span></span> <span data-ttu-id="58bc8-187">Estas son las ubicaciones de las distribuciones en las que se ha experimentado el problema.</span><span class="sxs-lookup"><span data-stu-id="58bc8-187">Here are the locations for the distros where the issue has been experienced.</span></span>

| <span data-ttu-id="58bc8-188">Distribución</span><span class="sxs-lookup"><span data-stu-id="58bc8-188">Distribution</span></span> | <span data-ttu-id="58bc8-189">Ubicación</span><span class="sxs-lookup"><span data-stu-id="58bc8-189">Location</span></span>                                            |
|--------------|-----------------------------------------------------|
| <span data-ttu-id="58bc8-190">**Fedora**</span><span class="sxs-lookup"><span data-stu-id="58bc8-190">**Fedora**</span></span>   | `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem` |
| <span data-ttu-id="58bc8-191">**OpenSUSE**</span><span class="sxs-lookup"><span data-stu-id="58bc8-191">**OpenSUSE**</span></span> | `/etc/ssl/ca-bundle.pem`                            |
| <span data-ttu-id="58bc8-192">**Solus**</span><span class="sxs-lookup"><span data-stu-id="58bc8-192">**Solus**</span></span>    | `/etc/ssl/certs/ca-certificates.crt`                |

## <a name="next-steps"></a><span data-ttu-id="58bc8-193">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="58bc8-193">Next steps</span></span>

- [<span data-ttu-id="58bc8-194">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="58bc8-194">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="58bc8-195">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="58bc8-195">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)

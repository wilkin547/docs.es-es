---
ms.openlocfilehash: 83808f2f3a05333ed5d9e3809cbc2fd6e230d02c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031786"
---

[<span data-ttu-id="eba04-101">.NET Core está disponible desde el almacén de snaps.</span><span class="sxs-lookup"><span data-stu-id="eba04-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="eba04-102">Un snap es una agrupación de una aplicación y sus dependencias que funcionan sin modificaciones en muchas distribuciones de Linux diferentes.</span><span class="sxs-lookup"><span data-stu-id="eba04-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="eba04-103">Los snaps se reconocen y se instalan desde el almacén de snaps.</span><span class="sxs-lookup"><span data-stu-id="eba04-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="eba04-104">Para más información sobre Snap, consulte [Introducción a Snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="eba04-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="eba04-105">Solo las versiones admitidas de .NET Core están disponibles mediante Snap.</span><span class="sxs-lookup"><span data-stu-id="eba04-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="eba04-106">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="eba04-106">Install the SDK</span></span>

<span data-ttu-id="eba04-107">Los paquetes Snap para el SDK de .NET se publican con el mismo identificador: `dotnet-sdk`.</span><span class="sxs-lookup"><span data-stu-id="eba04-107">Snap packages for .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="eba04-108">Se puede instalar una versión específica del SDK mediante la especificación del canal.</span><span class="sxs-lookup"><span data-stu-id="eba04-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="eba04-109">El SDK incluye el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="eba04-109">The SDK includes the corresponding runtime.</span></span> <span data-ttu-id="eba04-110">En la tabla siguiente se enumeran los canales:</span><span class="sxs-lookup"><span data-stu-id="eba04-110">The following table lists the channels:</span></span>

| <span data-ttu-id="eba04-111">Versión de .NET</span><span class="sxs-lookup"><span data-stu-id="eba04-111">.NET version</span></span> | <span data-ttu-id="eba04-112">Paquete Snap</span><span class="sxs-lookup"><span data-stu-id="eba04-112">Snap package</span></span>             |
|--------------|--------------------------|
| <span data-ttu-id="eba04-113">5.0</span><span class="sxs-lookup"><span data-stu-id="eba04-113">5.0</span></span>          | <span data-ttu-id="eba04-114">`5.0` o `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="eba04-114">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="eba04-115">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="eba04-115">3.1 (LTS)</span></span>    | <span data-ttu-id="eba04-116">`3.1` o `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="eba04-116">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="eba04-117">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="eba04-117">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="eba04-118">Use el comando `snap install` para instalar un paquete Snap del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="eba04-118">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="eba04-119">Use el parámetro `--channel` para indicar qué versión se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="eba04-119">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="eba04-120">Si se omite este parámetro, se usa `latest/stable`.</span><span class="sxs-lookup"><span data-stu-id="eba04-120">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="eba04-121">En este ejemplo, se especifica `5.0`:</span><span class="sxs-lookup"><span data-stu-id="eba04-121">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="eba04-122">A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="eba04-122">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="eba04-123">Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="eba04-123">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="eba04-124">Puede elegir cualquier nombre de `{alias}` que prefiera.</span><span class="sxs-lookup"><span data-stu-id="eba04-124">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="eba04-125">Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="eba04-125">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="eba04-126">Cuando use el comando `dotnet50`, invocará esta versión específica de .NET.</span><span class="sxs-lookup"><span data-stu-id="eba04-126">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="eba04-127">Sin embargo, esta operación no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="eba04-127">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="eba04-128">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="eba04-128">Install the runtime</span></span>

<span data-ttu-id="eba04-129">Los paquetes Snap de .NET Core Runtime se publican con su propio identificador de paquete.</span><span class="sxs-lookup"><span data-stu-id="eba04-129">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="eba04-130">En la tabla siguiente se muestra una lista de los identificadores de paquete:</span><span class="sxs-lookup"><span data-stu-id="eba04-130">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="eba04-131">Versión de .NET</span><span class="sxs-lookup"><span data-stu-id="eba04-131">.NET version</span></span>      | <span data-ttu-id="eba04-132">Paquete Snap</span><span class="sxs-lookup"><span data-stu-id="eba04-132">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="eba04-133">5.0</span><span class="sxs-lookup"><span data-stu-id="eba04-133">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="eba04-134">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="eba04-134">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="eba04-135">3.0</span><span class="sxs-lookup"><span data-stu-id="eba04-135">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="eba04-136">2.2</span><span class="sxs-lookup"><span data-stu-id="eba04-136">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="eba04-137">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="eba04-137">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="eba04-138">Use el comando `snap install` para instalar un paquete Snap del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="eba04-138">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="eba04-139">En este ejemplo, se instala .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="eba04-139">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="eba04-140">A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="eba04-140">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="eba04-141">Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="eba04-141">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="eba04-142">Puede elegir cualquier nombre de `{alias}` que prefiera.</span><span class="sxs-lookup"><span data-stu-id="eba04-142">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="eba04-143">Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span><span class="sxs-lookup"><span data-stu-id="eba04-143">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="eba04-144">Cuando use el comando `dotnet50`, invocará esta versión específica de .NET.</span><span class="sxs-lookup"><span data-stu-id="eba04-144">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="eba04-145">Sin embargo, esta operación no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="eba04-145">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="eba04-146">Errores de certificado SSL</span><span class="sxs-lookup"><span data-stu-id="eba04-146">SSL Certificate errors</span></span>

<span data-ttu-id="eba04-147">Cuando .NET se instala mediante Snap, es posible que en algunas distribuciones no se encuentren los certificados SSL de .NET y que reciba un error similar al siguiente durante la acción `restore`:</span><span class="sxs-lookup"><span data-stu-id="eba04-147">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="eba04-148">Para resolver este problema, establezca algunas variables de entorno:</span><span class="sxs-lookup"><span data-stu-id="eba04-148">To resolve this issue, set a few environment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="eba04-149">La ubicación del certificado variará en función de la distribución.</span><span class="sxs-lookup"><span data-stu-id="eba04-149">The certificate location will vary by distro.</span></span> <span data-ttu-id="eba04-150">Estas son las ubicaciones de las distribuciones en las que hemos experimentado el problema.</span><span class="sxs-lookup"><span data-stu-id="eba04-150">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="eba04-151">Fedora: `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="eba04-151">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="eba04-152">OpenSUSE: `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="eba04-152">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="eba04-153">Solus: `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="eba04-153">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>

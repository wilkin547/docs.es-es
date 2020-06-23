---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602691"
---

[<span data-ttu-id="074ff-101">.NET Core está disponible desde el almacén de snaps.</span><span class="sxs-lookup"><span data-stu-id="074ff-101">.NET Core is available from the Snap Store.</span></span>](https://snapcraft.io/dotnet-sdk)

<span data-ttu-id="074ff-102">Un snap es una agrupación de una aplicación y sus dependencias que funcionan sin modificaciones en muchas distribuciones de Linux diferentes.</span><span class="sxs-lookup"><span data-stu-id="074ff-102">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="074ff-103">Los snaps se reconocen y se instalan desde el almacén de snaps.</span><span class="sxs-lookup"><span data-stu-id="074ff-103">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="074ff-104">Para más información sobre Snap, consulte [Introducción a Snap](https://snapcraft.io/docs/getting-started).</span><span class="sxs-lookup"><span data-stu-id="074ff-104">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

<span data-ttu-id="074ff-105">Solo las versiones admitidas de .NET Core están disponibles mediante Snap.</span><span class="sxs-lookup"><span data-stu-id="074ff-105">Only supported versions of .NET Core are available through Snap.</span></span>

### <a name="install-the-sdk"></a><span data-ttu-id="074ff-106">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="074ff-106">Install the SDK</span></span>

<span data-ttu-id="074ff-107">Los paquetes Snap para el SDK de .NET Core se publican con el mismo identificador: `dotnet-sdk`.</span><span class="sxs-lookup"><span data-stu-id="074ff-107">Snap packages for .NET Core SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="074ff-108">Se puede instalar una versión específica del SDK mediante la especificación del canal.</span><span class="sxs-lookup"><span data-stu-id="074ff-108">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="074ff-109">El SDK incluye el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="074ff-109">The SDK includes the coresponding runtime.</span></span> <span data-ttu-id="074ff-110">En la tabla siguiente se enumeran los canales:</span><span class="sxs-lookup"><span data-stu-id="074ff-110">The following table list the channels:</span></span>

| <span data-ttu-id="074ff-111">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="074ff-111">.NET Core version</span></span> | <span data-ttu-id="074ff-112">Paquete Snap</span><span class="sxs-lookup"><span data-stu-id="074ff-112">Snap package</span></span>             |
|-------------------|--------------------------|
| <span data-ttu-id="074ff-113">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="074ff-113">3.1 (LTS)</span></span>         | <span data-ttu-id="074ff-114">`3.1` o `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="074ff-114">`3.1` or `latest/stable`</span></span> |
| <span data-ttu-id="074ff-115">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="074ff-115">2.1 (LTS)</span></span>         | `2.1`                    |
| <span data-ttu-id="074ff-116">.NET 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="074ff-116">.NET 5.0 preview</span></span>  | `5.0/beta`               |

<span data-ttu-id="074ff-117">Use el comando `snap install` para instalar un paquete Snap del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="074ff-117">Use the `snap install` command to install a .NET Core SDK snap package.</span></span> <span data-ttu-id="074ff-118">Use el parámetro `--channel` para indicar qué versión se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="074ff-118">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="074ff-119">Si se omite este parámetro, se usa `latest/stable`.</span><span class="sxs-lookup"><span data-stu-id="074ff-119">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="074ff-120">En este ejemplo, se especifica `3.1`:</span><span class="sxs-lookup"><span data-stu-id="074ff-120">In this example, `3.1` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

<span data-ttu-id="074ff-121">A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="074ff-121">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="074ff-122">Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="074ff-122">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="074ff-123">Puede elegir cualquier nombre de `{alias}` que prefiera.</span><span class="sxs-lookup"><span data-stu-id="074ff-123">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="074ff-124">Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span><span class="sxs-lookup"><span data-stu-id="074ff-124">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet31`.</span></span> <span data-ttu-id="074ff-125">Cuando use el comando `dotnet31`, invocará esta versión específica de .NET.</span><span class="sxs-lookup"><span data-stu-id="074ff-125">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="074ff-126">Sin embargo, esta operación no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="074ff-126">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="074ff-127">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="074ff-127">Install the runtime</span></span>

<span data-ttu-id="074ff-128">Los paquetes Snap de .NET Core Runtime se publican con su propio identificador de paquete.</span><span class="sxs-lookup"><span data-stu-id="074ff-128">Snap packages for .NET Core Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="074ff-129">En la tabla siguiente se muestra una lista de los identificadores de paquete:</span><span class="sxs-lookup"><span data-stu-id="074ff-129">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="074ff-130">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="074ff-130">.NET Core version</span></span> | <span data-ttu-id="074ff-131">Paquete Snap</span><span class="sxs-lookup"><span data-stu-id="074ff-131">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="074ff-132">3.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="074ff-132">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="074ff-133">3.0</span><span class="sxs-lookup"><span data-stu-id="074ff-133">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="074ff-134">2.2</span><span class="sxs-lookup"><span data-stu-id="074ff-134">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="074ff-135">2.1 (LTS)</span><span class="sxs-lookup"><span data-stu-id="074ff-135">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="074ff-136">Use el comando `snap install` para instalar un paquete Snap de .NET Core Runtime.</span><span class="sxs-lookup"><span data-stu-id="074ff-136">Use the `snap install` command to install a .NET Core Runtime snap package.</span></span> <span data-ttu-id="074ff-137">En este ejemplo, se instala .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="074ff-137">In this example, .NET Core 3.1 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-31 --classic
```

<span data-ttu-id="074ff-138">A continuación, registre el comando `dotnet` del sistema con el comando `snap alias`:</span><span class="sxs-lookup"><span data-stu-id="074ff-138">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

<span data-ttu-id="074ff-139">Este comando tiene el formato `sudo snap alias {package}.{command} {alias}`.</span><span class="sxs-lookup"><span data-stu-id="074ff-139">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="074ff-140">Puede elegir cualquier nombre de `{alias}` que prefiera.</span><span class="sxs-lookup"><span data-stu-id="074ff-140">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="074ff-141">Por ejemplo, puede asignar un nombre al comando después de la versión específica instalada por el snap `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span><span class="sxs-lookup"><span data-stu-id="074ff-141">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31`.</span></span> <span data-ttu-id="074ff-142">Cuando use el comando `dotnet31`, invocará esta versión específica de .NET.</span><span class="sxs-lookup"><span data-stu-id="074ff-142">When you use the command `dotnet31`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="074ff-143">Sin embargo, esta operación no es compatible con la mayoría de los tutoriales y ejemplos, donde se espera que esté disponible un comando `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="074ff-143">But this is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

### <a name="ssl-certificate-errors"></a><span data-ttu-id="074ff-144">Errores de certificado SSL</span><span class="sxs-lookup"><span data-stu-id="074ff-144">SSL Certificate errors</span></span>

<span data-ttu-id="074ff-145">Cuando .NET se instala mediante Snap, es posible que en algunas distribuciones no se encuentren los certificados SSL de .NET y que reciba un error similar al siguiente durante la acción `restore`:</span><span class="sxs-lookup"><span data-stu-id="074ff-145">When .NET is installed through Snap, it's possible that on some distros the .NET SSL certificates may not be found and you may receive an error similar to the following during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="074ff-146">Para resolver este problema, establezca algunas variables de entorno:</span><span class="sxs-lookup"><span data-stu-id="074ff-146">To resolve this issue, set a few enviornment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="074ff-147">La ubicación del certificado variará en función de la distribución.</span><span class="sxs-lookup"><span data-stu-id="074ff-147">The certificate location will vary by distro.</span></span> <span data-ttu-id="074ff-148">Estas son las ubicaciones de las distribuciones en las que hemos experimentado el problema.</span><span class="sxs-lookup"><span data-stu-id="074ff-148">Here are the locations for the distros where we have experienced the issue.</span></span>

* <span data-ttu-id="074ff-149">Fedora: `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="074ff-149">Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`</span></span>
* <span data-ttu-id="074ff-150">OpenSUSE: `/etc/ssl/ca-bundle.pem`</span><span class="sxs-lookup"><span data-stu-id="074ff-150">OpenSUSE - `/etc/ssl/ca-bundle.pem`</span></span>
* <span data-ttu-id="074ff-151">Solus: `/etc/ssl/certs/ca-certificates.crt`</span><span class="sxs-lookup"><span data-stu-id="074ff-151">Solus - `/etc/ssl/certs/ca-certificates.crt`</span></span>

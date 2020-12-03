---
title: 'Instalación de .NET en RHEL: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 931cad51ff8e35ff16b67ff9b795feb36010a66b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031790"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="090c1-103">Instalación del SDK y el entorno de ejecución de .NET en RHEL</span><span class="sxs-lookup"><span data-stu-id="090c1-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="090c1-104">.NET es compatible con RHEL.</span><span class="sxs-lookup"><span data-stu-id="090c1-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="090c1-105">En este artículo se describe cómo instalar .NET en RHEL.</span><span class="sxs-lookup"><span data-stu-id="090c1-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="090c1-106">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="090c1-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="090c1-107">Para instalar .NET desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="090c1-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="090c1-108">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="090c1-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="090c1-109">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="090c1-109">Supported distributions</span></span>

<span data-ttu-id="090c1-110">En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con RHEL 7 y RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="090c1-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="090c1-111">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="090c1-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="090c1-112">El símbolo ✔️ indica que todavía se admite la versión de RHEL o de .NET.</span><span class="sxs-lookup"><span data-stu-id="090c1-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="090c1-113">El símbolo ❌ indica que la versión de RHEL o de .NET no se admite en esa versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="090c1-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="090c1-114">Si una versión de RHEL y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="090c1-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="090c1-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="090c1-115">RHEL</span></span>                     | <span data-ttu-id="090c1-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="090c1-116">.NET Core 2.1</span></span> | <span data-ttu-id="090c1-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="090c1-117">.NET Core 3.1</span></span> | <span data-ttu-id="090c1-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="090c1-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="090c1-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="090c1-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="090c1-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="090c1-120">✔️ 2.1</span></span>        | <span data-ttu-id="090c1-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="090c1-121">✔️ 3.1</span></span>        | <span data-ttu-id="090c1-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="090c1-122">✔️ 5.0</span></span> |
| <span data-ttu-id="090c1-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="090c1-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="090c1-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="090c1-124">✔️ 2.1</span></span>        | <span data-ttu-id="090c1-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="090c1-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="090c1-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="090c1-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="090c1-127">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="090c1-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="090c1-128">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="090c1-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="090c1-129">3.0</span><span class="sxs-lookup"><span data-stu-id="090c1-129">3.0</span></span>
- <span data-ttu-id="090c1-130">2.2</span><span class="sxs-lookup"><span data-stu-id="090c1-130">2.2</span></span>
- <span data-ttu-id="090c1-131">2.0</span><span class="sxs-lookup"><span data-stu-id="090c1-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="090c1-132">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="090c1-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="090c1-133">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="090c1-133">How to install other versions</span></span>

<span data-ttu-id="090c1-134">Consulte la [documentación de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/) sobre los pasos necesarios para instalar otras versiones de .NET.</span><span class="sxs-lookup"><span data-stu-id="090c1-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="090c1-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="090c1-135">RHEL 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="090c1-136">.NET 5.0 todavía no está disponible en los repositorios de AppStream, pero .NET Core 3.1 sí.</span><span class="sxs-lookup"><span data-stu-id="090c1-136">.NET 5.0 isn't yet available in the AppStream repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="090c1-137">Para instalar .NET Core 3.1, use el comando `dnf install` con el paquete adecuado, como `aspnetcore-runtime-3.1` o `dotnet-sdk-3.1`.</span><span class="sxs-lookup"><span data-stu-id="090c1-137">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="090c1-138">Las siguientes instrucciones son para .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="090c1-138">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/8/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="090c1-139">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="090c1-139">RHEL 7 ✔️ .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/rhel/7/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-yum.md)]

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="090c1-140">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="090c1-140">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="090c1-141">El siguiente comando instala el paquete `scl-utils`:</span><span class="sxs-lookup"><span data-stu-id="090c1-141">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="090c1-142">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="090c1-142">Install the SDK</span></span>

<span data-ttu-id="090c1-143">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="090c1-143">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="090c1-144">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="090c1-144">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="090c1-145">Para instalar el SDK de .NET Core, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="090c1-145">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="090c1-146">Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="090c1-146">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="090c1-147">Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="090c1-147">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="090c1-148">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="090c1-148">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="090c1-149">Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="090c1-149">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="090c1-150">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="090c1-150">Install the runtime</span></span>

<span data-ttu-id="090c1-151">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="090c1-151">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="090c1-152">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="090c1-152">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="090c1-153">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="090c1-153">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="090c1-154">Red Hat no recomienda habilitar `rh-dotnet31-aspnetcore-runtime-3.1` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="090c1-154">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="090c1-155">Por ejemplo, `rh-dotnet31-aspnetcore-runtime-3.1` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="090c1-155">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="090c1-156">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="090c1-156">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="090c1-157">Si quiere habilitar `rh-dotnet31-aspnetcore-runtime-3.1` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="090c1-157">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="090c1-158">Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet31-aspnetcore-runtime-3.1` en los comandos anteriores por `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="090c1-158">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="090c1-159">Snap</span><span class="sxs-lookup"><span data-stu-id="090c1-159">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="090c1-160">Dependencias</span><span class="sxs-lookup"><span data-stu-id="090c1-160">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="090c1-161">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="090c1-161">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="090c1-162">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="090c1-162">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="090c1-163">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="090c1-163">Next steps</span></span>

- [<span data-ttu-id="090c1-164">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="090c1-164">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)

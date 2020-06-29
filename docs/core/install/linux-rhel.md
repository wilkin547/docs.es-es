---
title: 'Instalación de .NET Core en RHEL: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en RHEL.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 4a406fe1834c16bab9a5548b69206b51270b33fa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324719"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a><span data-ttu-id="c7a3b-103">Instalación del SDK de .NET Core o de .NET Core Runtime en RHEL</span><span class="sxs-lookup"><span data-stu-id="c7a3b-103">Install .NET Core SDK or .NET Core Runtime on RHEL</span></span>

<span data-ttu-id="c7a3b-104">.NET Core es compatible con RHEL.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-104">.NET Core is supported on RHEL.</span></span> <span data-ttu-id="c7a3b-105">En este artículo se describe cómo instalar .NET Core en RHEL.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-105">This article describes how to install .NET Core on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="c7a3b-106">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="c7a3b-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="c7a3b-107">Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="c7a3b-108">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).</span><span class="sxs-lookup"><span data-stu-id="c7a3b-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="c7a3b-109">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="c7a3b-109">Supported distributions</span></span>

<span data-ttu-id="c7a3b-110">En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente con RHEL 7 y RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-110">The following table is a list of currently supported .NET Core releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="c7a3b-111">Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="c7a3b-112">Una ✔️ indica que todavía se admite la versión de RHEL o de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-112">A ✔️ indicates that the version of RHEL or .NET Core is still supported.</span></span>
- <span data-ttu-id="c7a3b-113">Una ❌ indica que la versión de RHEL o de .NET Core no se admite en esa versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-113">A ❌ indicates that the version of RHEL or .NET Core isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="c7a3b-114">Cuando una versión de RHEL y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-114">When both a version of RHEL and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="c7a3b-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="c7a3b-115">RHEL</span></span>                   | <span data-ttu-id="c7a3b-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c7a3b-116">.NET Core 2.1</span></span> | <span data-ttu-id="c7a3b-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c7a3b-117">.NET Core 3.1</span></span> | <span data-ttu-id="c7a3b-118">Versión preliminar de .NET 5 (solo instalación manual)</span><span class="sxs-lookup"><span data-stu-id="c7a3b-118">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="c7a3b-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="c7a3b-119">✔️ [8](#rhel-8-)</span></span> | <span data-ttu-id="c7a3b-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="c7a3b-120">✔️ 2.1</span></span>        | <span data-ttu-id="c7a3b-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="c7a3b-121">✔️ 3.1</span></span>        | <span data-ttu-id="c7a3b-122">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c7a3b-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="c7a3b-123">✔️ [7](#rhel-7-)</span><span class="sxs-lookup"><span data-stu-id="c7a3b-123">✔️ [7](#rhel-7-)</span></span> | <span data-ttu-id="c7a3b-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="c7a3b-124">✔️ 2.1</span></span>        | <span data-ttu-id="c7a3b-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="c7a3b-125">✔️ 3.1</span></span>        | <span data-ttu-id="c7a3b-126">✔️ 5.0 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c7a3b-126">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="c7a3b-127">Las siguientes versiones de .NET Core ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-127">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="c7a3b-128">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="c7a3b-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="c7a3b-129">3.0</span><span class="sxs-lookup"><span data-stu-id="c7a3b-129">3.0</span></span>
- <span data-ttu-id="c7a3b-130">2.2</span><span class="sxs-lookup"><span data-stu-id="c7a3b-130">2.2</span></span>
- <span data-ttu-id="c7a3b-131">2.0</span><span class="sxs-lookup"><span data-stu-id="c7a3b-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c7a3b-132">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="c7a3b-132">How to install other versions</span></span>

<span data-ttu-id="c7a3b-133">Consulte la [documentación de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/) sobre los pasos necesarios para instalar otras versiones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-133">Consult the [Red Hat documentation for .NET Core](https://access.redhat.com/documentation/net_core/) on the steps required to install other releases of .NET Core.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="c7a3b-134">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="c7a3b-134">RHEL 8 ✔️</span></span>

<span data-ttu-id="c7a3b-135">.NET Core se incluye en los repositorios de AppStream para RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-135">.NET Core is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a><span data-ttu-id="c7a3b-136">RHEL 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="c7a3b-136">RHEL 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="c7a3b-137">El siguiente comando instala el paquete `scl-utils`:</span><span class="sxs-lookup"><span data-stu-id="c7a3b-137">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="c7a3b-138">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="c7a3b-138">Install the SDK</span></span>

<span data-ttu-id="c7a3b-139">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-139">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="c7a3b-140">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-140">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="c7a3b-141">Para instalar el SDK de .NET Core, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="c7a3b-141">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="c7a3b-142">Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-142">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="c7a3b-143">Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-143">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="c7a3b-144">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-144">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="c7a3b-145">Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-145">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="c7a3b-146">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c7a3b-146">Install the runtime</span></span>

<span data-ttu-id="c7a3b-147">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-147">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="c7a3b-148">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-148">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="c7a3b-149">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-149">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="c7a3b-150">Red Hat no recomienda habilitar `rh-dotnet31-aspnetcore-runtime-3.1` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-150">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="c7a3b-151">Por ejemplo, `rh-dotnet31-aspnetcore-runtime-3.1` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-151">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="c7a3b-152">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-152">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="c7a3b-153">Si quiere habilitar `rh-dotnet31-aspnetcore-runtime-3.1` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-153">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="c7a3b-154">Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet31-aspnetcore-runtime-3.1` en los comandos anteriores por `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="c7a3b-154">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="c7a3b-155">Snap</span><span class="sxs-lookup"><span data-stu-id="c7a3b-155">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="c7a3b-156">Dependencias</span><span class="sxs-lookup"><span data-stu-id="c7a3b-156">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="c7a3b-157">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="c7a3b-157">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="c7a3b-158">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="c7a3b-158">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="c7a3b-159">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c7a3b-159">Next steps</span></span>

- [<span data-ttu-id="c7a3b-160">Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c7a3b-160">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)

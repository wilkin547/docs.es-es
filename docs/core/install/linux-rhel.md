---
title: 'Instalación de .NET en RHEL: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 0b6138185bfd3e2f50c1b31e82779165715a5b6e
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851645"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="4bfd4-103">Instalación del SDK y el entorno de ejecución de .NET en RHEL</span><span class="sxs-lookup"><span data-stu-id="4bfd4-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="4bfd4-104">.NET es compatible con RHEL.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="4bfd4-105">En este artículo se describe cómo instalar .NET en RHEL.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="4bfd4-106">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="4bfd4-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="4bfd4-107">Para instalar .NET desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="4bfd4-108">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="4bfd4-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="4bfd4-109">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="4bfd4-109">Supported distributions</span></span>

<span data-ttu-id="4bfd4-110">En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con RHEL 7 y RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="4bfd4-111">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="4bfd4-112">El símbolo ✔️ indica que todavía se admite la versión de RHEL o de .NET.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="4bfd4-113">El símbolo ❌ indica que la versión de RHEL o de .NET no se admite en esa versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="4bfd4-114">Si una versión de RHEL y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="4bfd4-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="4bfd4-115">RHEL</span></span>                     | <span data-ttu-id="4bfd4-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4bfd4-116">.NET Core 2.1</span></span> | <span data-ttu-id="4bfd4-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="4bfd4-117">.NET Core 3.1</span></span> | <span data-ttu-id="4bfd4-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="4bfd4-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="4bfd4-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="4bfd4-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="4bfd4-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="4bfd4-120">✔️ 2.1</span></span>        | <span data-ttu-id="4bfd4-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="4bfd4-121">✔️ 3.1</span></span>        | <span data-ttu-id="4bfd4-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="4bfd4-122">✔️ 5.0</span></span> |
| <span data-ttu-id="4bfd4-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="4bfd4-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="4bfd4-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="4bfd4-124">✔️ 2.1</span></span>        | <span data-ttu-id="4bfd4-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="4bfd4-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="4bfd4-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="4bfd4-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="4bfd4-127">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="4bfd4-128">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="4bfd4-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="4bfd4-129">3.0</span><span class="sxs-lookup"><span data-stu-id="4bfd4-129">3.0</span></span>
- <span data-ttu-id="4bfd4-130">2.2</span><span class="sxs-lookup"><span data-stu-id="4bfd4-130">2.2</span></span>
- <span data-ttu-id="4bfd4-131">2.0</span><span class="sxs-lookup"><span data-stu-id="4bfd4-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="4bfd4-132">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="4bfd4-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="4bfd4-133">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="4bfd4-133">How to install other versions</span></span>

<span data-ttu-id="4bfd4-134">Consulte la [documentación de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/) sobre los pasos necesarios para instalar otras versiones de .NET.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-134">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="4bfd4-135">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="4bfd4-135">RHEL 8 ✔️</span></span>

<span data-ttu-id="4bfd4-136">.NET se incluye en los repositorios de AppStream para RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-136">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="4bfd4-137">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="4bfd4-137">RHEL 7 ✔️ .NET 5.0</span></span>

<span data-ttu-id="4bfd4-138">El siguiente comando instala el paquete `scl-utils`:</span><span class="sxs-lookup"><span data-stu-id="4bfd4-138">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="4bfd4-139">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="4bfd4-139">Install the SDK</span></span>

<span data-ttu-id="4bfd4-140">El SDK de .NET permite desarrollar aplicaciones con .NET.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-140">The .NET SDK allows you to develop apps with .NET .</span></span> <span data-ttu-id="4bfd4-141">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-141">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="4bfd4-142">Para instalar el SDK de .NET, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4bfd4-142">To install .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="4bfd4-143">Red Hat no recomienda habilitar `rh-dotnet50` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-143">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="4bfd4-144">Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-144">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="4bfd4-145">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4bfd4-145">Install the runtime</span></span>

<span data-ttu-id="4bfd4-146">El entorno de ejecución de .NET permite ejecutar aplicaciones creadas con .NET, pero sin incluir el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-146">The .NET Runtime allows you to run apps that were made with .NET that didn't include the runtime.</span></span> <span data-ttu-id="4bfd4-147">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-147">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="4bfd4-148">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-148">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="4bfd4-149">Red Hat no recomienda habilitar `rh-dotnet50` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-149">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="4bfd4-150">Si quiere habilitar `rh-dotnet50` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-150">If you want to enable `rh-dotnet50` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

<span data-ttu-id="4bfd4-151">Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET, que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet50-aspnetcore-runtime-5.0` en los comandos anteriores por `rh-dotnet50-dotnet-runtime-5.0`.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-151">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the commands above with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="4bfd4-152">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="4bfd4-152">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="4bfd4-153">El siguiente comando instala el paquete `scl-utils`:</span><span class="sxs-lookup"><span data-stu-id="4bfd4-153">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="4bfd4-154">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="4bfd4-154">Install the SDK</span></span>

<span data-ttu-id="4bfd4-155">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-155">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="4bfd4-156">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-156">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="4bfd4-157">Para instalar el SDK de .NET Core, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="4bfd4-157">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="4bfd4-158">Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-158">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="4bfd4-159">Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-159">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="4bfd4-160">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-160">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="4bfd4-161">Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-161">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="4bfd4-162">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4bfd4-162">Install the runtime</span></span>

<span data-ttu-id="4bfd4-163">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-163">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="4bfd4-164">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-164">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="4bfd4-165">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-165">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="4bfd4-166">Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-166">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="4bfd4-167">Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-167">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="4bfd4-168">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-168">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="4bfd4-169">Si quiere habilitar `rh-dotnet31` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-169">If you want to enable `rh-dotnet31` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

<span data-ttu-id="4bfd4-170">Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet31-aspnetcore-runtime-3.1` en los comandos anteriores por `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="4bfd4-170">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="4bfd4-171">Snap</span><span class="sxs-lookup"><span data-stu-id="4bfd4-171">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="4bfd4-172">Dependencias</span><span class="sxs-lookup"><span data-stu-id="4bfd4-172">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="4bfd4-173">Instalación con script</span><span class="sxs-lookup"><span data-stu-id="4bfd4-173">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="4bfd4-174">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="4bfd4-174">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="4bfd4-175">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4bfd4-175">Next steps</span></span>

- [<span data-ttu-id="4bfd4-176">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4bfd4-176">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)

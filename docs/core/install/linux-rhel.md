---
title: 'Instalación de .NET en RHEL: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en RHEL.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: d585017919507a8fdcbb24778a0ff3ab3d9049c2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970803"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a><span data-ttu-id="11d64-103">Instalación del SDK y el entorno de ejecución de .NET en RHEL</span><span class="sxs-lookup"><span data-stu-id="11d64-103">Install the .NET SDK or the .NET Runtime on RHEL</span></span>

<span data-ttu-id="11d64-104">.NET es compatible con RHEL.</span><span class="sxs-lookup"><span data-stu-id="11d64-104">.NET is supported on RHEL.</span></span> <span data-ttu-id="11d64-105">En este artículo se describe cómo instalar .NET en RHEL.</span><span class="sxs-lookup"><span data-stu-id="11d64-105">This article describes how to install .NET on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="11d64-106">Registro de la suscripción de Red Hat</span><span class="sxs-lookup"><span data-stu-id="11d64-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="11d64-107">Para instalar .NET desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat.</span><span class="sxs-lookup"><span data-stu-id="11d64-107">To install .NET from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="11d64-108">Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/).</span><span class="sxs-lookup"><span data-stu-id="11d64-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET](https://access.redhat.com/documentation/net/5.0/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="11d64-109">Distribuciones admitidas</span><span class="sxs-lookup"><span data-stu-id="11d64-109">Supported distributions</span></span>

<span data-ttu-id="11d64-110">En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con RHEL 7 y RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="11d64-110">The following table is a list of currently supported .NET releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="11d64-111">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="11d64-111">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="11d64-112">El símbolo ✔️ indica que todavía se admite la versión de RHEL o de .NET.</span><span class="sxs-lookup"><span data-stu-id="11d64-112">A ✔️ indicates that the version of RHEL or .NET is still supported.</span></span>
- <span data-ttu-id="11d64-113">El símbolo ❌ indica que la versión de RHEL o de .NET no se admite en esa versión de RHEL.</span><span class="sxs-lookup"><span data-stu-id="11d64-113">A ❌ indicates that the version of RHEL or .NET isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="11d64-114">Si una versión de RHEL y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.</span><span class="sxs-lookup"><span data-stu-id="11d64-114">When both a version of RHEL and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="11d64-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="11d64-115">RHEL</span></span>                     | <span data-ttu-id="11d64-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="11d64-116">.NET Core 2.1</span></span> | <span data-ttu-id="11d64-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="11d64-117">.NET Core 3.1</span></span> | <span data-ttu-id="11d64-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="11d64-118">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="11d64-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="11d64-119">✔️ [8](#rhel-8-)</span></span>        | <span data-ttu-id="11d64-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="11d64-120">✔️ 2.1</span></span>        | <span data-ttu-id="11d64-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="11d64-121">✔️ 3.1</span></span>        | <span data-ttu-id="11d64-122">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="11d64-122">✔️ 5.0</span></span> |
| <span data-ttu-id="11d64-123">✔️ [7](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="11d64-123">✔️ [7](#rhel-7--net-50)</span></span> | <span data-ttu-id="11d64-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="11d64-124">✔️ 2.1</span></span>        | <span data-ttu-id="11d64-125">✔️ [3.1](#rhel-7--net-core-31)</span><span class="sxs-lookup"><span data-stu-id="11d64-125">✔️ [3.1](#rhel-7--net-core-31)</span></span>        | <span data-ttu-id="11d64-126">✔️ [5.0](#rhel-7--net-50)</span><span class="sxs-lookup"><span data-stu-id="11d64-126">✔️ [5.0](#rhel-7--net-50)</span></span> |

<span data-ttu-id="11d64-127">Las versiones siguientes de .NET ya no se admiten.</span><span class="sxs-lookup"><span data-stu-id="11d64-127">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="11d64-128">Las descargas de estas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="11d64-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="11d64-129">3.0</span><span class="sxs-lookup"><span data-stu-id="11d64-129">3.0</span></span>
- <span data-ttu-id="11d64-130">2.2</span><span class="sxs-lookup"><span data-stu-id="11d64-130">2.2</span></span>
- <span data-ttu-id="11d64-131">2.0</span><span class="sxs-lookup"><span data-stu-id="11d64-131">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="11d64-132">Eliminación de versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="11d64-132">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="rhel-8-"></a><span data-ttu-id="11d64-133">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="11d64-133">RHEL 8 ✔️</span></span>

<span data-ttu-id="11d64-134">.NET se incluye en los repositorios de AppStream para RHEL 8.</span><span class="sxs-lookup"><span data-stu-id="11d64-134">.NET is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a><span data-ttu-id="11d64-135">RHEL 7 ✔️ .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="11d64-135">RHEL 7 ✔️ .NET 5.0</span></span>

<span data-ttu-id="11d64-136">El siguiente comando instala el paquete `scl-utils`:</span><span class="sxs-lookup"><span data-stu-id="11d64-136">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="11d64-137">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="11d64-137">Install the SDK</span></span>

<span data-ttu-id="11d64-138">El SDK de .NET permite desarrollar aplicaciones con .NET.</span><span class="sxs-lookup"><span data-stu-id="11d64-138">The .NET SDK allows you to develop apps with .NET .</span></span> <span data-ttu-id="11d64-139">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="11d64-139">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="11d64-140">Para instalar el SDK de .NET, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="11d64-140">To install .NET SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="11d64-141">Red Hat no recomienda habilitar `rh-dotnet50` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="11d64-141">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="11d64-142">Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="11d64-142">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a><span data-ttu-id="11d64-143">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="11d64-143">Install the runtime</span></span>

<span data-ttu-id="11d64-144">El entorno de ejecución de .NET permite ejecutar aplicaciones creadas con .NET, pero sin incluir el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11d64-144">The .NET Runtime allows you to run apps that were made with .NET that didn't include the runtime.</span></span> <span data-ttu-id="11d64-145">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="11d64-145">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="11d64-146">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="11d64-146">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

<span data-ttu-id="11d64-147">Red Hat no recomienda habilitar `rh-dotnet50` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="11d64-147">Red Hat does not recommend permanently enabling `rh-dotnet50` because it may affect other programs.</span></span> <span data-ttu-id="11d64-148">Si quiere habilitar `rh-dotnet50` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="11d64-148">If you want to enable `rh-dotnet50` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet50
```

<span data-ttu-id="11d64-149">Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET, que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet50-aspnetcore-runtime-5.0` en los comandos anteriores por `rh-dotnet50-dotnet-runtime-5.0`.</span><span class="sxs-lookup"><span data-stu-id="11d64-149">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet50-aspnetcore-runtime-5.0` in the commands above with `rh-dotnet50-dotnet-runtime-5.0`.</span></span>

## <a name="rhel-7--net-core-31"></a><span data-ttu-id="11d64-150">RHEL 7 ✔️ .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="11d64-150">RHEL 7 ✔️ .NET Core 3.1</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="11d64-151">El siguiente comando instala el paquete `scl-utils`:</span><span class="sxs-lookup"><span data-stu-id="11d64-151">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="11d64-152">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="11d64-152">Install the SDK</span></span>

<span data-ttu-id="11d64-153">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="11d64-153">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="11d64-154">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="11d64-154">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="11d64-155">Para instalar el SDK de .NET Core, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="11d64-155">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="11d64-156">Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="11d64-156">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="11d64-157">Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="11d64-157">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="11d64-158">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="11d64-158">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="11d64-159">Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="11d64-159">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="11d64-160">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="11d64-160">Install the runtime</span></span>

<span data-ttu-id="11d64-161">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11d64-161">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="11d64-162">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="11d64-162">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="11d64-163">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="11d64-163">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="11d64-164">Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas.</span><span class="sxs-lookup"><span data-stu-id="11d64-164">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="11d64-165">Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL.</span><span class="sxs-lookup"><span data-stu-id="11d64-165">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="11d64-166">Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`.</span><span class="sxs-lookup"><span data-stu-id="11d64-166">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="11d64-167">Si quiere habilitar `rh-dotnet31` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.</span><span class="sxs-lookup"><span data-stu-id="11d64-167">If you want to enable `rh-dotnet31` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

<span data-ttu-id="11d64-168">Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet31-aspnetcore-runtime-3.1` en los comandos anteriores por `rh-dotnet31-dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="11d64-168">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="dependencies"></a><span data-ttu-id="11d64-169">Dependencias</span><span class="sxs-lookup"><span data-stu-id="11d64-169">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="11d64-170">Procedimiento para instalar otras versiones</span><span class="sxs-lookup"><span data-stu-id="11d64-170">How to install other versions</span></span>

<span data-ttu-id="11d64-171">Consulte la [documentación de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/) sobre los pasos necesarios para instalar otras versiones de .NET.</span><span class="sxs-lookup"><span data-stu-id="11d64-171">Consult the [Red Hat documentation for .NET](https://access.redhat.com/documentation/net/5.0/) on the steps required to install other releases of .NET.</span></span>

## <a name="next-steps"></a><span data-ttu-id="11d64-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="11d64-172">Next steps</span></span>

- [<span data-ttu-id="11d64-173">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="11d64-173">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="11d64-174">Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="11d64-174">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)

---
title: Catálogo de identificadores de entorno de ejecución (RID) de .NET Core
description: Obtenga información sobre el identificador en tiempo de ejecución (RID) y sobre cómo se usan los RID en .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.openlocfilehash: 81f9e5f65385bbd81c7fdae7f75c62d11b6f6319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215915"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="b6d39-103">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b6d39-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="b6d39-104">RID es la abreviatura de *identificador de entorno de ejecución*.</span><span class="sxs-lookup"><span data-stu-id="b6d39-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="b6d39-105">Los valores de RID se usan para identificar las plataformas de destino donde se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6d39-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="b6d39-106">Los paquetes de .NET los usan para presentar los recursos específicos de la plataforma en los paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="b6d39-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="b6d39-107">Los valores siguientes son ejemplos de RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` o `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="b6d39-108">En el caso de los paquetes con dependencias nativas, el RID designa las plataformas en las que se puede restauran el paquete.</span><span class="sxs-lookup"><span data-stu-id="b6d39-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="b6d39-109">Un único RID se puede establecer en el elemento `<RuntimeIdentifier>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6d39-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="b6d39-110">Se pueden definir varios RID como una lista delimitada por punto y coma en el elemento `<RuntimeIdentifiers>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6d39-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="b6d39-111">También se usan a través de la opción `--runtime` con los [comandos de la CLI de .NET Core](./tools/index.md) siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6d39-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="b6d39-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b6d39-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="b6d39-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b6d39-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="b6d39-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b6d39-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="b6d39-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b6d39-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="b6d39-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b6d39-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="b6d39-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b6d39-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="b6d39-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="b6d39-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="b6d39-119">Los RID que representan sistemas operativos concretos normalmente siguen este patrón: `[os].[version]-[architecture]-[additional qualifiers]`, donde:</span><span class="sxs-lookup"><span data-stu-id="b6d39-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="b6d39-120">`[os]` es el moniker del sistema operativo o de plataforma.</span><span class="sxs-lookup"><span data-stu-id="b6d39-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="b6d39-121">Por ejemplo: `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="b6d39-122">`[version]` es la versión del sistema operativo en formato de número de versión separado por punto (`.`).</span><span class="sxs-lookup"><span data-stu-id="b6d39-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="b6d39-123">Por ejemplo: `15.10`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="b6d39-124">La versión **no** se debe tratar como versiones de marketing, debido a que, a menudo, representan varias versiones discretas del sistema operativo con un área expuesta de API de plataforma diferente.</span><span class="sxs-lookup"><span data-stu-id="b6d39-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="b6d39-125">`[architecture]` es la arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="b6d39-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="b6d39-126">Por ejemplo: `x86`, `x64`, `arm` o `arm64`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="b6d39-127">`[additional qualifiers]` diferencia aún más las distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="b6d39-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="b6d39-128">Por ejemplo: `aot` o `corert`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-128">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="b6d39-129">Grafo de RID</span><span class="sxs-lookup"><span data-stu-id="b6d39-129">RID graph</span></span>

<span data-ttu-id="b6d39-130">El grado de RID o el grafo de reserva de entorno de ejecución es una lista de RID compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="b6d39-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="b6d39-131">Los RID se definen en el paquete [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/).</span><span class="sxs-lookup"><span data-stu-id="b6d39-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="b6d39-132">Pude ver la lista de RID compatibles y el grafo de RID en el archivo [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json), que se encuentra en el repositorio de CoreFX.</span><span class="sxs-lookup"><span data-stu-id="b6d39-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="b6d39-133">En este archivo puede ver que todos los RID, excepto el RID de base, contienen una instrucción `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="b6d39-134">Estas instrucciones indican los RID compatibles.</span><span class="sxs-lookup"><span data-stu-id="b6d39-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="b6d39-135">Cuando NuGet restaura los paquetes, intenta encontrar una coincidencia exacta para el entorno de ejecución especificado.</span><span class="sxs-lookup"><span data-stu-id="b6d39-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="b6d39-136">Si no se encuentra una coincidencia exacta, NuGet vuelve al grafo hasta encontrar el sistema compatible más cercano según el grafo de RID.</span><span class="sxs-lookup"><span data-stu-id="b6d39-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="b6d39-137">El ejemplo siguiente es la entrada real del RID `osx.10.12-x64`:</span><span class="sxs-lookup"><span data-stu-id="b6d39-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="b6d39-138">El RID anterior especifica que `osx.10.12-x64` importa `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="b6d39-139">Por tanto, cuando NuGet restaura los paquetes, intenta encontrar una coincidencia exacta para `osx.10.12-x64` en el paquete.</span><span class="sxs-lookup"><span data-stu-id="b6d39-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="b6d39-140">Si NuGet no puede encontrar el entorno de ejecución específico, puede restaurar, por ejemplo, los paquetes que especifican entornos de ejecución `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="b6d39-141">En el ejemplo siguiente se muestra un grafo de RID ligeramente más grande que también se define en el archivo *runtime.json*:</span><span class="sxs-lookup"><span data-stu-id="b6d39-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="b6d39-142">A la larga, todos los RID se asignarán de vuelta al RID `any` raíz.</span><span class="sxs-lookup"><span data-stu-id="b6d39-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="b6d39-143">Hay algunas consideraciones sobre los RID que debe tener en cuenta cuando trabaja con ellos:</span><span class="sxs-lookup"><span data-stu-id="b6d39-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="b6d39-144">Los RID son **cadenas opacas** y se deben tratar como cajas negras.</span><span class="sxs-lookup"><span data-stu-id="b6d39-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="b6d39-145">No compile RID mediante programación.</span><span class="sxs-lookup"><span data-stu-id="b6d39-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="b6d39-146">Use RID que ya estén definidos para la plataforma.</span><span class="sxs-lookup"><span data-stu-id="b6d39-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="b6d39-147">Los RID deben ser específicos, por lo que no se recomienda presuponer nada a partir del valor de RID real.</span><span class="sxs-lookup"><span data-stu-id="b6d39-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="b6d39-148">Uso de los RID</span><span class="sxs-lookup"><span data-stu-id="b6d39-148">Using RIDs</span></span>

<span data-ttu-id="b6d39-149">Para poder usar los RID, debe saber cuáles son los RID que existen.</span><span class="sxs-lookup"><span data-stu-id="b6d39-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="b6d39-150">Se agregan valores nuevos a la plataforma de manera habitual.</span><span class="sxs-lookup"><span data-stu-id="b6d39-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="b6d39-151">Para obtener la versión más reciente y completa, consulte el archivo [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) que se encuentra en el repositorio CoreFX.</span><span class="sxs-lookup"><span data-stu-id="b6d39-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="b6d39-152">El SDK de .NET Core 2.0 presenta el concepto de RID portátiles.</span><span class="sxs-lookup"><span data-stu-id="b6d39-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="b6d39-153">Se trata de valores nuevos agregados al grafo de RID que no están vinculados a una versión específica o a una distribución de SO específica.</span><span class="sxs-lookup"><span data-stu-id="b6d39-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="b6d39-154">Resultan especialmente útiles cuando se trabaja con varias distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="b6d39-154">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="b6d39-155">En la lista siguiente se muestran los RID más comunes que se usan en cada SO.</span><span class="sxs-lookup"><span data-stu-id="b6d39-155">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="b6d39-156">No se abarcan los valores `arm` o `corert`.</span><span class="sxs-lookup"><span data-stu-id="b6d39-156">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="b6d39-157">RID de Windows</span><span class="sxs-lookup"><span data-stu-id="b6d39-157">Windows RIDs</span></span>

- <span data-ttu-id="b6d39-158">Portátil</span><span class="sxs-lookup"><span data-stu-id="b6d39-158">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="b6d39-159">Windows 7/Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b6d39-159">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="b6d39-160">Windows 8/Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b6d39-160">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="b6d39-161">Windows 8.1/Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b6d39-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="b6d39-162">Windows 10/Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b6d39-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="b6d39-163">Vea [Requisitos previos para .NET Core en Windows](windows-prerequisites.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="b6d39-163">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="b6d39-164">RID de Linux</span><span class="sxs-lookup"><span data-stu-id="b6d39-164">Linux RIDs</span></span>

- <span data-ttu-id="b6d39-165">Portátil</span><span class="sxs-lookup"><span data-stu-id="b6d39-165">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="b6d39-166">CentOS</span><span class="sxs-lookup"><span data-stu-id="b6d39-166">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="b6d39-167">Debian</span><span class="sxs-lookup"><span data-stu-id="b6d39-167">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="b6d39-168">Fedora</span><span class="sxs-lookup"><span data-stu-id="b6d39-168">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="b6d39-169">`fedora.25-x64` (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-169">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="b6d39-170">`fedora.26-x64` (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-170">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="b6d39-171">Gentoo (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-171">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="b6d39-172">openSUSE</span><span class="sxs-lookup"><span data-stu-id="b6d39-172">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="b6d39-173">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="b6d39-173">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="b6d39-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="b6d39-174">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="b6d39-175">`rhel.6-x64` (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="b6d39-176">`rhel.7.3-x64` (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-176">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="b6d39-177">`rhel.7.4-x64` (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-177">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="b6d39-178">Tizen (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-178">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="b6d39-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b6d39-179">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="b6d39-180">Derivados de Ubuntu</span><span class="sxs-lookup"><span data-stu-id="b6d39-180">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="b6d39-181">`linuxmint.18.1-x64` (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-181">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="b6d39-182">Vea [Requisitos previos para .NET Core en Linux](linux-prerequisites.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="b6d39-182">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="b6d39-183">RID de macOS</span><span class="sxs-lookup"><span data-stu-id="b6d39-183">macOS RIDs</span></span>

<span data-ttu-id="b6d39-184">Los RID de macOS usan la personalización de marca antigua "OSX".</span><span class="sxs-lookup"><span data-stu-id="b6d39-184">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="b6d39-185">`osx-x64` (.NET Core 2.0 o versiones posteriores, la versión mínima es `osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="b6d39-185">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="b6d39-186">`osx.10.12-x64` (.NET Core 1.1 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-186">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="b6d39-187">Vea [Requisitos previos para .NET Core en macOS](macos-prerequisites.md) para más información.</span><span class="sxs-lookup"><span data-stu-id="b6d39-187">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="b6d39-188">RID de Android (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="b6d39-188">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="b6d39-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6d39-189">See also</span></span>

[<span data-ttu-id="b6d39-190">Identificadores de entorno de ejecución</span><span class="sxs-lookup"><span data-stu-id="b6d39-190">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)

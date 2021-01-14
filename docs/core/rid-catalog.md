---
title: Catálogo de identificadores de entorno de ejecución (RID) de .NET Core
description: Obtenga información sobre el identificador en tiempo de ejecución (RID) y sobre cómo se usan los RID en .NET Core.
ms.date: 12/15/2020
ms.openlocfilehash: f818ab2d503be7960d9eb8450a7dd749766637a6
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633616"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="a90f8-103">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a90f8-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="a90f8-104">RID es la abreviatura de *identificador de entorno de ejecución*.</span><span class="sxs-lookup"><span data-stu-id="a90f8-104">RID is short for *Runtime Identifier*.</span></span> <span data-ttu-id="a90f8-105">Los valores de RID se usan para identificar las plataformas de destino donde se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a90f8-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="a90f8-106">Los paquetes de .NET los usan para presentar los recursos específicos de la plataforma en los paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a90f8-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="a90f8-107">Los valores siguientes son ejemplos de RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` o `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="a90f8-108">En el caso de los paquetes con dependencias nativas, el RID designa las plataformas en las que se puede restauran el paquete.</span><span class="sxs-lookup"><span data-stu-id="a90f8-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="a90f8-109">Un único RID se puede establecer en el elemento `<RuntimeIdentifier>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a90f8-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="a90f8-110">Se pueden definir varios RID como una lista delimitada por punto y coma en el elemento `<RuntimeIdentifiers>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a90f8-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="a90f8-111">También se usan a través de la opción `--runtime` con los [comandos de la CLI de .NET Core](./tools/index.md) siguientes:</span><span class="sxs-lookup"><span data-stu-id="a90f8-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="a90f8-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="a90f8-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="a90f8-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="a90f8-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="a90f8-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="a90f8-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="a90f8-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="a90f8-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="a90f8-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="a90f8-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="a90f8-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="a90f8-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="a90f8-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="a90f8-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="a90f8-119">Los RID que representan sistemas operativos concretos normalmente siguen este patrón: `[os].[version]-[architecture]-[additional qualifiers]`, donde:</span><span class="sxs-lookup"><span data-stu-id="a90f8-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="a90f8-120">`[os]` es el moniker del sistema operativo o de plataforma.</span><span class="sxs-lookup"><span data-stu-id="a90f8-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="a90f8-121">Por ejemplo: `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="a90f8-122">`[version]` es la versión del sistema operativo en formato de número de versión separado por punto (`.`).</span><span class="sxs-lookup"><span data-stu-id="a90f8-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="a90f8-123">Por ejemplo: `15.10`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="a90f8-124">La versión **no** se debe tratar como versiones de marketing, debido a que, a menudo, representan varias versiones discretas del sistema operativo con un área expuesta de API de plataforma diferente.</span><span class="sxs-lookup"><span data-stu-id="a90f8-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="a90f8-125">`[architecture]` es la arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="a90f8-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="a90f8-126">Por ejemplo: `x86`, `x64`, `arm` o `arm64`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="a90f8-127">`[additional qualifiers]` diferencia aún más las distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="a90f8-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="a90f8-128">Por ejemplo: `aot`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-128">For example: `aot`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="a90f8-129">Grafo de RID</span><span class="sxs-lookup"><span data-stu-id="a90f8-129">RID graph</span></span>

<span data-ttu-id="a90f8-130">El grado de RID o el grafo de reserva de entorno de ejecución es una lista de RID compatibles entre sí.</span><span class="sxs-lookup"><span data-stu-id="a90f8-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="a90f8-131">Los RID se definen en el paquete [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/).</span><span class="sxs-lookup"><span data-stu-id="a90f8-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="a90f8-132">Puede ver la lista de RID compatibles y el grafo de RID en el archivo [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json), que se encuentra en el repositorio `dotnet/runtime`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the `dotnet/runtime` repository.</span></span> <span data-ttu-id="a90f8-133">En este archivo puede ver que todos los RID, excepto el RID de base, contienen una instrucción `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="a90f8-134">Estas instrucciones indican los RID compatibles.</span><span class="sxs-lookup"><span data-stu-id="a90f8-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="a90f8-135">Cuando NuGet restaura los paquetes, intenta encontrar una coincidencia exacta para el entorno de ejecución especificado.</span><span class="sxs-lookup"><span data-stu-id="a90f8-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="a90f8-136">Si no se encuentra una coincidencia exacta, NuGet vuelve al grafo hasta encontrar el sistema compatible más cercano según el grafo de RID.</span><span class="sxs-lookup"><span data-stu-id="a90f8-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="a90f8-137">El ejemplo siguiente es la entrada real del RID `osx.10.12-x64`:</span><span class="sxs-lookup"><span data-stu-id="a90f8-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="a90f8-138">El RID anterior especifica que `osx.10.12-x64` importa `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="a90f8-139">Por tanto, cuando NuGet restaura los paquetes, intenta encontrar una coincidencia exacta para `osx.10.12-x64` en el paquete.</span><span class="sxs-lookup"><span data-stu-id="a90f8-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="a90f8-140">Si NuGet no puede encontrar el entorno de ejecución específico, puede restaurar, por ejemplo, los paquetes que especifican entornos de ejecución `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="a90f8-141">En el ejemplo siguiente se muestra un grafo de RID ligeramente más grande que también se define en el archivo *runtime.json*:</span><span class="sxs-lookup"><span data-stu-id="a90f8-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

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

<span data-ttu-id="a90f8-142">A la larga, todos los RID se asignarán de vuelta al RID `any` raíz.</span><span class="sxs-lookup"><span data-stu-id="a90f8-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="a90f8-143">Hay algunas consideraciones sobre los RID que debe tener en cuenta cuando trabaja con ellos:</span><span class="sxs-lookup"><span data-stu-id="a90f8-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="a90f8-144">No intente analizar los RID para recuperar partes de componentes.</span><span class="sxs-lookup"><span data-stu-id="a90f8-144">Don't try to parse RIDs to retrieve component parts.</span></span>
- <span data-ttu-id="a90f8-145">No compile RID mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a90f8-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="a90f8-146">Use RID que ya estén definidos para la plataforma.</span><span class="sxs-lookup"><span data-stu-id="a90f8-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="a90f8-147">Los RID deben ser específicos, por lo que no se recomienda presuponer nada a partir del valor de RID real.</span><span class="sxs-lookup"><span data-stu-id="a90f8-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="a90f8-148">Uso de los RID</span><span class="sxs-lookup"><span data-stu-id="a90f8-148">Using RIDs</span></span>

<span data-ttu-id="a90f8-149">Para poder usar los RID, debe saber cuáles son los RID que existen.</span><span class="sxs-lookup"><span data-stu-id="a90f8-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="a90f8-150">Se agregan valores nuevos a la plataforma de manera habitual.</span><span class="sxs-lookup"><span data-stu-id="a90f8-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="a90f8-151">Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

<span data-ttu-id="a90f8-152">El SDK de .NET Core 2.0 presenta el concepto de RID portátiles.</span><span class="sxs-lookup"><span data-stu-id="a90f8-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="a90f8-153">Son nuevos valores agregados al grafo de RID que no están vinculados a una versión específica o distribución del sistema operativo, y son la opción preferida cuando se usa .NET Core 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a90f8-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution and are the preferred choice when using .NET Core 2.0 and higher.</span></span> <span data-ttu-id="a90f8-154">Resultan especialmente útiles al tratar con varias distribuciones de Linux dado que la mayoría de los RID de distribución se asignan a los RID portátiles.</span><span class="sxs-lookup"><span data-stu-id="a90f8-154">They're particularly useful when dealing with multiple Linux distros since most distribution RIDs are mapped to the portable RIDs.</span></span>

<span data-ttu-id="a90f8-155">En la lista siguiente se muestra un pequeño subconjunto de los RID más comunes que se usan con cada sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a90f8-155">The following list shows a small subset of the most common RIDs used for each OS.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="a90f8-156">RID de Windows</span><span class="sxs-lookup"><span data-stu-id="a90f8-156">Windows RIDs</span></span>

<span data-ttu-id="a90f8-157">Solo se muestran los valores comunes.</span><span class="sxs-lookup"><span data-stu-id="a90f8-157">Only common values are listed.</span></span> <span data-ttu-id="a90f8-158">Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-158">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="a90f8-159">Portátil (.NET Core 2.0 o versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="a90f8-159">Portable (.NET Core 2.0 or later versions)</span></span>
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- <span data-ttu-id="a90f8-160">Windows 7/Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a90f8-160">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="a90f8-161">Windows 8.1/Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a90f8-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="a90f8-162">Windows 10/Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a90f8-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="a90f8-163">Para obtener más información, vea [Dependencias y requisitos de .NET Core](./install/windows.md#dependencies) .</span><span class="sxs-lookup"><span data-stu-id="a90f8-163">For more information, see [.NET Core dependencies and requirements](./install/windows.md#dependencies).</span></span>

## <a name="linux-rids"></a><span data-ttu-id="a90f8-164">RID de Linux</span><span class="sxs-lookup"><span data-stu-id="a90f8-164">Linux RIDs</span></span>

<span data-ttu-id="a90f8-165">Solo se muestran los valores comunes.</span><span class="sxs-lookup"><span data-stu-id="a90f8-165">Only common values are listed.</span></span> <span data-ttu-id="a90f8-166">Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-166">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span> <span data-ttu-id="a90f8-167">Los dispositivos que ejecutan una distribución que no se muestran en la lista podrían funcionar con uno de los RID portátiles.</span><span class="sxs-lookup"><span data-stu-id="a90f8-167">Devices running a distribution not listed below may work with one of the Portable RIDs.</span></span> <span data-ttu-id="a90f8-168">Por ejemplo, el destino de los dispositivos Raspberry Pi que ejecutan una distribución de Linux se puede establecer con `linux-arm`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-168">For example, Raspberry Pi devices running a Linux distribution not listed can be targeted with `linux-arm`.</span></span>

- <span data-ttu-id="a90f8-169">Portátil</span><span class="sxs-lookup"><span data-stu-id="a90f8-169">Portable</span></span>
  - <span data-ttu-id="a90f8-170">`linux-x64` (La mayoría de las distribuciones de escritorio como CentOS, Debian, Fedora, Ubuntu y derivados)</span><span class="sxs-lookup"><span data-stu-id="a90f8-170">`linux-x64` (Most desktop distributions like CentOS, Debian, Fedora, Ubuntu, and derivatives)</span></span>
  - <span data-ttu-id="a90f8-171">`linux-musl-x64` (Distribuciones ligeras con [musl](https://wiki.musl-libc.org/projects-using-musl.html) como Alpine Linux)</span><span class="sxs-lookup"><span data-stu-id="a90f8-171">`linux-musl-x64` (Lightweight distributions using [musl](https://wiki.musl-libc.org/projects-using-musl.html) like Alpine Linux)</span></span>
  - <span data-ttu-id="a90f8-172">`linux-arm` (Distribuciones de Linux que se ejecutan en ARM, como Raspbian en Raspberry Pi, modelo 2+)</span><span class="sxs-lookup"><span data-stu-id="a90f8-172">`linux-arm` (Linux distributions running on ARM like Raspbian on Raspberry Pi Model 2+)</span></span>
  - <span data-ttu-id="a90f8-173">`linux-arm64` (Distribuciones de Linux que se ejecutan en ARM de 64 bits, como Ubuntu Server de 64 bits en Raspberry Pi, modelo 3+)</span><span class="sxs-lookup"><span data-stu-id="a90f8-173">`linux-arm64` (Linux distributions running on 64-bit ARM like Ubuntu Server 64-bit on Raspberry Pi Model 3+)</span></span>
- <span data-ttu-id="a90f8-174">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a90f8-174">Red Hat Enterprise Linux</span></span>
  - <span data-ttu-id="a90f8-175">`rhel-x64` (Se reemplaza por `linux-x64` para RHEL por encima de la versión 6)</span><span class="sxs-lookup"><span data-stu-id="a90f8-175">`rhel-x64` (Superseded by `linux-x64` for RHEL above version 6)</span></span>
  - `rhel.6-x64`
- <span data-ttu-id="a90f8-176">Tizen</span><span class="sxs-lookup"><span data-stu-id="a90f8-176">Tizen</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

<span data-ttu-id="a90f8-177">Para obtener más información, vea [Dependencias y requisitos de .NET Core](./install/linux.md) .</span><span class="sxs-lookup"><span data-stu-id="a90f8-177">For more information, see [.NET Core dependencies and requirements](./install/linux.md).</span></span>

## <a name="macos-rids"></a><span data-ttu-id="a90f8-178">RID de macOS</span><span class="sxs-lookup"><span data-stu-id="a90f8-178">macOS RIDs</span></span>

<span data-ttu-id="a90f8-179">Los RID de macOS usan la personalización de marca antigua "OSX".</span><span class="sxs-lookup"><span data-stu-id="a90f8-179">macOS RIDs use the older "OSX" branding.</span></span> <span data-ttu-id="a90f8-180">Solo se muestran los valores comunes.</span><span class="sxs-lookup"><span data-stu-id="a90f8-180">Only common values are listed.</span></span> <span data-ttu-id="a90f8-181">Para obtener la versión más reciente y completa, vea el archivo [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) en el repositorio `dotnet/runtime`.</span><span class="sxs-lookup"><span data-stu-id="a90f8-181">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="a90f8-182">Portátil</span><span class="sxs-lookup"><span data-stu-id="a90f8-182">Portable</span></span>
  - <span data-ttu-id="a90f8-183">`osx-x64` (La versión mínima del sistema operativo es macOS 10.12 Sierra)</span><span class="sxs-lookup"><span data-stu-id="a90f8-183">`osx-x64` (Minimum OS version is macOS 10.12 Sierra)</span></span>
- <span data-ttu-id="a90f8-184">macOS 10.10  Yosemite</span><span class="sxs-lookup"><span data-stu-id="a90f8-184">macOS 10.10  Yosemite</span></span>
  - `osx.10.10-x64`
- <span data-ttu-id="a90f8-185">macOS 10.11 El Capitan</span><span class="sxs-lookup"><span data-stu-id="a90f8-185">macOS 10.11 El Capitan</span></span>
  - `osx.10.11-x64`
- <span data-ttu-id="a90f8-186">macOS 10.12 Sierra</span><span class="sxs-lookup"><span data-stu-id="a90f8-186">macOS 10.12 Sierra</span></span>
  - `osx.10.12-x64`
- <span data-ttu-id="a90f8-187">macOS 10.13 High Sierra</span><span class="sxs-lookup"><span data-stu-id="a90f8-187">macOS 10.13 High Sierra</span></span>
  - `osx.10.13-x64`
- <span data-ttu-id="a90f8-188">macOS 10.14 Mojave</span><span class="sxs-lookup"><span data-stu-id="a90f8-188">macOS 10.14 Mojave</span></span>
  - `osx.10.14-x64`
- <span data-ttu-id="a90f8-189">macOS 10.15 Catalina</span><span class="sxs-lookup"><span data-stu-id="a90f8-189">macOS 10.15 Catalina</span></span>
  - `osx.10.15-x64`
- <span data-ttu-id="a90f8-190">macOS 11.01 Big Sur</span><span class="sxs-lookup"><span data-stu-id="a90f8-190">macOS 11.01 Big Sur</span></span>
  - `osx.11.0-x64`
  - `osx.11.0-arm64`

<span data-ttu-id="a90f8-191">Para obtener más información, vea [Dependencias y requisitos de .NET Core](./install/macos.md#dependencies) .</span><span class="sxs-lookup"><span data-stu-id="a90f8-191">For more information, see [.NET Core dependencies and requirements](./install/macos.md#dependencies).</span></span>

## <a name="see-also"></a><span data-ttu-id="a90f8-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="a90f8-192">See also</span></span>

- [<span data-ttu-id="a90f8-193">Identificadores de entorno de ejecución</span><span class="sxs-lookup"><span data-stu-id="a90f8-193">Runtime IDs</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)

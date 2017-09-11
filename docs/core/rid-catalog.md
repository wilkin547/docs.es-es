---
title: "Catálogo de identificadores de entorno de ejecución (RID) de .NET Core"
description: "Obtenga información sobre el identificador en tiempo de ejecución (RID) y sobre cómo se usan los RID en .NET Core."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/22/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b2032f5d-771f-48d9-917c-587d9509035c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3490fb639efd223dc36190324bdf3a06bc23c10e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-runtime-identifier-rid-catalog"></a><span data-ttu-id="e608a-104">Catálogo de identificadores de entorno de ejecución (RID) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e608a-104">.NET Core Runtime IDentifier (RID) catalog</span></span>

## <a name="what-are-rids"></a><span data-ttu-id="e608a-105">¿Qué son los RID?</span><span class="sxs-lookup"><span data-stu-id="e608a-105">What are RIDs?</span></span>
<span data-ttu-id="e608a-106">RID es la abreviatura de *identificador de entorno de ejecución*.</span><span class="sxs-lookup"><span data-stu-id="e608a-106">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="e608a-107">Los RID se usan para identificar los sistemas operativos de destino donde se ejecutará una aplicación o un recurso (es decir, un ensamblado).</span><span class="sxs-lookup"><span data-stu-id="e608a-107">RIDs are used to identify target operating systems where an application or asset (that is, assembly) will run.</span></span> <span data-ttu-id="e608a-108">Tienen el siguiente aspecto: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64".</span><span class="sxs-lookup"><span data-stu-id="e608a-108">They look like this: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64".</span></span> <span data-ttu-id="e608a-109">En el caso de los paquetes con dependencias nativas, designará las plataformas en las que se puede restaurar el paquete.</span><span class="sxs-lookup"><span data-stu-id="e608a-109">For the packages with native dependencies, it will designate on which platforms the package can be restored.</span></span> 

<span data-ttu-id="e608a-110">Es importante tener en cuenta que los RID son, en realidad, cadenas opacas.</span><span class="sxs-lookup"><span data-stu-id="e608a-110">It is important to note that RIDs are really opaque strings.</span></span> <span data-ttu-id="e608a-111">Esto significa que deben coincidir de manera exacta para que las operaciones las usen en algún trabajo.</span><span class="sxs-lookup"><span data-stu-id="e608a-111">This means that they have to match exactly for operations using them to work.</span></span> <span data-ttu-id="e608a-112">Como ejemplo, consideremos el caso de [Elementary OS](https://elementary.io/), un clon sencillo de Ubuntu 14.04.</span><span class="sxs-lookup"><span data-stu-id="e608a-112">As an example, let us consider the case of [Elementary OS](https://elementary.io/), which is a straightforward clone of Ubuntu 14.04.</span></span> <span data-ttu-id="e608a-113">A pesar de que .NET Core y la CLI funcionan sobre esa versión de Ubuntu, si intenta usarlas en Elementary OS sin ninguna modificación, se producirá un error en la operación de restauración de cualquier paquete.</span><span class="sxs-lookup"><span data-stu-id="e608a-113">Although .NET Core and CLI work on top of that version of Ubuntu, if you try to use them on Elementary OS without any modifications, the restore operation for any package will fail.</span></span> <span data-ttu-id="e608a-114">Esto sucede porque actualmente no tenemos un RID que designe a Elementary OS como plataforma.</span><span class="sxs-lookup"><span data-stu-id="e608a-114">This is because we currently don't have a RID that designates Elementary OS as a platform.</span></span> 

<span data-ttu-id="e608a-115">Los RID que representan sistemas operativos concretos normalmente siguen este patrón: `[os].[version]-[arch]`, donde:</span><span class="sxs-lookup"><span data-stu-id="e608a-115">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[arch]` where:</span></span>
- <span data-ttu-id="e608a-116">`[os]` es el moniker del sistema operativo, por ejemplo `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="e608a-116">`[os]` is the operating system moniker, for example, `ubuntu`.</span></span>
- <span data-ttu-id="e608a-117">`[version]` es la versión del sistema operativo con formato de número de versión separada por punto (`.`), por ejemplo `15.10`; es lo suficientemente preciso para habilitar de manera razonable los recursos a fin de que usen como destino las API de plataforma de sistema operativo que representa esa versión.</span><span class="sxs-lookup"><span data-stu-id="e608a-117">`[version]` is the operating system version in the form of a dot (`.`) separated version number, for example, `15.10`, accurate enough to reasonably enable assets to target operating system platform APIs represented by that version.</span></span>
  - <span data-ttu-id="e608a-118">**No** se deben tratar como versiones de marketing, debido a que, a menudo, representan varias versiones discretas del sistema operativo con un área expuesta de API de plataforma diferente.</span><span class="sxs-lookup"><span data-stu-id="e608a-118">This **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>
- <span data-ttu-id="e608a-119">`[arch]` es la arquitectura del procesador, por ejemplo, `x86`, `x64`, `arm`, `arm64`, etc.</span><span class="sxs-lookup"><span data-stu-id="e608a-119">`[arch]` is the processor architecture, for example, `x86`, `x64`, `arm`, `arm64`, etc.</span></span>

<span data-ttu-id="e608a-120">El gráfico de los RID está definido en un paquete llamado `Microsoft.NETCore.Platforms` en un archivo llamado `runtime.json`, que puede ver en el [repositorio de CoreFX](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span><span class="sxs-lookup"><span data-stu-id="e608a-120">The RID graph is defined in a package called `Microsoft.NETCore.Platforms` in a file called `runtime.json`, which you can see on the [CoreFX repo](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span></span> <span data-ttu-id="e608a-121">Si usa este archivo, verá que algunos de los RID tienen una instrucción `"#import"`.</span><span class="sxs-lookup"><span data-stu-id="e608a-121">If you use this file, you will notice that some of the RIDs have an `"#import"` statement in them.</span></span> <span data-ttu-id="e608a-122">Se trata de instrucciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="e608a-122">These statements are compatibility statements.</span></span> <span data-ttu-id="e608a-123">Esto significa que un RID que tiene importado un RID puede ser un destino para la restauración de los paquetes de ese RID.</span><span class="sxs-lookup"><span data-stu-id="e608a-123">That means that a RID that has an imported RID in it can be a target for restoring packages for that RID.</span></span> <span data-ttu-id="e608a-124">Probablemente sea un poco confuso, pero mejor veamos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e608a-124">Slightly confusing, but let's look at an example.</span></span> <span data-ttu-id="e608a-125">Echemos un vistazo a macOS:</span><span class="sxs-lookup"><span data-stu-id="e608a-125">Let's take a look at macOS:</span></span>

```json
"osx.10.11-x64": {
    "#import": [ "osx.10.11", "osx.10.10-x64" ]
}
```
<span data-ttu-id="e608a-126">El RID anterior especifica que `osx.10.11-x64` importa `osx.10.10-x64`.</span><span class="sxs-lookup"><span data-stu-id="e608a-126">The above RID specifies that `osx.10.11-x64` imports `osx.10.10-x64`.</span></span> <span data-ttu-id="e608a-127">Esto significa que, cuando se restauran los paquetes, NuGet podrá restaurar los paquetes que especifiquen que necesitan `osx.10.10-x64` en `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="e608a-127">This means that when restoring packages, NuGet will be able to restore packages that specify that they need `osx.10.10-x64` on `osx.10.11-x64`.</span></span>

<span data-ttu-id="e608a-128">El ejemplo de un gráfico de RID levemente más grande:</span><span class="sxs-lookup"><span data-stu-id="e608a-128">A slightly bigger example RID graph:</span></span>  

- `win10-arm`
  - `win10`
  - `win81-arm`
    - `win81`
    - `win8-arm`
      - `win8`
        - `win7`
          - `win`
            - `any`

<span data-ttu-id="e608a-129">A la larga, todos los RID se asignarán de vuelta al RID `any` raíz.</span><span class="sxs-lookup"><span data-stu-id="e608a-129">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="e608a-130">A pesar de que se ven muy fáciles de usar, hay algunos aspectos especiales de los RID que debe considerar cuando trabaja con ellos:</span><span class="sxs-lookup"><span data-stu-id="e608a-130">Although they look easy enough to use, there are some special things about RIDs that you have to keep in mind when working with them:</span></span>

* <span data-ttu-id="e608a-131">Son **cadenas opacas** y se deben tratar como cajas negras.</span><span class="sxs-lookup"><span data-stu-id="e608a-131">They are **opaque strings** and should be treated as black boxes</span></span>
    * <span data-ttu-id="e608a-132">No debe construir los RID mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e608a-132">You should not construct RIDs programmatically</span></span>
* <span data-ttu-id="e608a-133">Debe usar los RID que ya están definidos para la plataforma y este documento así lo muestra.</span><span class="sxs-lookup"><span data-stu-id="e608a-133">You need to use the RIDs that are already defined for the platform and this document shows that</span></span>
* <span data-ttu-id="e608a-134">Los RID deben ser específicos para que no supongan nada más allá del valor real del RID. Consulte este documento para determinar los RID que necesita para una plataforma determinada.</span><span class="sxs-lookup"><span data-stu-id="e608a-134">The RIDs do need to be specific so don't assume anything from the actual RID value; please consult this document to determine which RID(s) you need for a given platform</span></span>

## <a name="using-rids"></a><span data-ttu-id="e608a-135">Uso de los RID</span><span class="sxs-lookup"><span data-stu-id="e608a-135">Using RIDs</span></span>
<span data-ttu-id="e608a-136">Para usar los RID, debe saber con qué RID cuenta.</span><span class="sxs-lookup"><span data-stu-id="e608a-136">In order to use RIDs, you have to know which RIDs there are.</span></span> <span data-ttu-id="e608a-137">Se agregan RID nuevos a la plataforma de manera habitual.</span><span class="sxs-lookup"><span data-stu-id="e608a-137">New RIDs are added regularly to the platform.</span></span> <span data-ttu-id="e608a-138">Para obtener la versión más reciente, revise el archivo [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) que se encuentra en el repositorio CoreFX.</span><span class="sxs-lookup"><span data-stu-id="e608a-138">For the latest version, please check the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

> [!NOTE]
> <span data-ttu-id="e608a-139">Estamos trabajando para que esta información se convierta en un formato más interactivo.</span><span class="sxs-lookup"><span data-stu-id="e608a-139">We are working towards getting this information into a more interactive form.</span></span> <span data-ttu-id="e608a-140">Cuando eso suceda, se actualizará esta página para que tenga como destino la herramienta o su documentación de uso.</span><span class="sxs-lookup"><span data-stu-id="e608a-140">When that happens, this page will be updated to point to that tool and/or its usage documentation.</span></span> 

## <a name="windows-rids"></a><span data-ttu-id="e608a-141">RID de Windows</span><span class="sxs-lookup"><span data-stu-id="e608a-141">Windows RIDs</span></span>

* <span data-ttu-id="e608a-142">Windows 7/Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e608a-142">Windows 7 / Windows Server 2008 R2</span></span>
    * `win7-x64`
    * `win7-x86`
* <span data-ttu-id="e608a-143">Windows 8/Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e608a-143">Windows 8 / Windows Server 2012</span></span>
    * `win8-x64`
    * `win8-x86`
    * `win8-arm`
* <span data-ttu-id="e608a-144">Windows 8.1/Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e608a-144">Windows 8.1 / Windows Server 2012 R2</span></span>
    * `win81-x64`
    * `win81-x86`
    * `win81-arm`
* <span data-ttu-id="e608a-145">Windows 10/Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e608a-145">Windows 10 / Windows Server 2016</span></span>
    * `win10-x64`
    * `win10-x86`
    * `win10-arm`
    * `win10-arm64`

## <a name="linux-rids"></a><span data-ttu-id="e608a-146">RID de Linux</span><span class="sxs-lookup"><span data-stu-id="e608a-146">Linux RIDs</span></span>

* <span data-ttu-id="e608a-147">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="e608a-147">Red Hat Enterprise Linux</span></span>
    * `rhel.7-x64`
* <span data-ttu-id="e608a-148">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e608a-148">Ubuntu</span></span>
    * `ubuntu.14.04-x64`
    * `ubuntu.14.10-x64`
    * `ubuntu.15.04-x64`
    * `ubuntu.15.10-x64`
    * `ubuntu.16.04-x64`
    * `ubuntu.16.10-x64`
* <span data-ttu-id="e608a-149">CentOS</span><span class="sxs-lookup"><span data-stu-id="e608a-149">CentOS</span></span>
    * `centos.7-x64`
* <span data-ttu-id="e608a-150">Debian</span><span class="sxs-lookup"><span data-stu-id="e608a-150">Debian</span></span>
    * `debian.8-x64`
* <span data-ttu-id="e608a-151">Fedora</span><span class="sxs-lookup"><span data-stu-id="e608a-151">Fedora</span></span>
    * `fedora.23-x64`
    * `fedora.24-x64`
* <span data-ttu-id="e608a-152">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="e608a-152">OpenSUSE</span></span>
    * `opensuse.13.2-x64`
    * `opensuse.42.1-x64`
* <span data-ttu-id="e608a-153">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="e608a-153">Oracle Linux</span></span>
    * `ol.7-x64`
    * `ol.7.0-x64`
    * `ol.7.1-x64`
    * `ol.7.2-x64`
* <span data-ttu-id="e608a-154">Derivadas de Ubuntu admitidas actualmente</span><span class="sxs-lookup"><span data-stu-id="e608a-154">Currently supported Ubuntu derivatives</span></span> 
    * `linuxmint.17-x64`
    * `linuxmint.17.1-x64`
    * `linuxmint.17.2-x64`
    * `linuxmint.17.3-x64`
    * `linuxmint.18-x64`

## <a name="os-x-rids"></a><span data-ttu-id="e608a-155">RID de OS X</span><span class="sxs-lookup"><span data-stu-id="e608a-155">OS X RIDs</span></span>

* `osx.10.10-x64`
* `osx.10.11-x64`
* `osx.10.12-x64`


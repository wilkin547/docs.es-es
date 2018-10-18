---
title: Nombres seguros y las bibliotecas de .NET
description: Prácticas recomendadas para las bibliotecas de .NET nomenclatura seguras.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372814"
---
# <a name="strong-naming"></a><span data-ttu-id="47dd5-103">Nombres seguros</span><span class="sxs-lookup"><span data-stu-id="47dd5-103">Strong naming</span></span>

<span data-ttu-id="47dd5-104">Nombres seguros se refiere al firmar un ensamblado con una clave, generar un [ensamblados](../../framework/app-domains/strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="47dd5-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../../framework/app-domains/strong-named-assemblies.md).</span></span> <span data-ttu-id="47dd5-105">Una vez un ensamblado con nombre seguro, crea una identidad única en función del número de versión de nombre y el ensamblado, y puede ayudar a evitar conflictos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="47dd5-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="47dd5-106">La desventaja de nombre seguro es que .NET Framework en Windows permite strict carga de ensamblados una vez que un ensamblado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="47dd5-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="47dd5-107">Una referencia de ensamblado con nombre seguro debe coincidir exactamente con la versión que se hace referencia a un ensamblado, los desarrolladores a [configurar redirecciones de enlace](../../framework/configure-apps/redirect-assembly-versions.md) cuando se usa el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="47dd5-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="47dd5-108">Cuando los desarrolladores de .NET se quejan nombres seguros, lo están normalmente queja es strict carga de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="47dd5-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="47dd5-109">Afortunadamente, este problema está aislado en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47dd5-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="47dd5-110">La mayoría de otras implementaciones. NET, Xamarin, UWP y .NET core no tiene la carga de ensamblados estricta y quita la principal desventaja de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="47dd5-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="47dd5-111">Un aspecto importante de nombre seguro es que resulta viral: una fuerte denominado ensamblado sólo pueden hacer referencia otros seguro ensamblados con nombre.</span><span class="sxs-lookup"><span data-stu-id="47dd5-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="47dd5-112">Si la biblioteca no está segura con nombre, a continuación, ha excluido a los desarrolladores que crean una aplicación o biblioteca que necesita nombres seguros de utilizarla.</span><span class="sxs-lookup"><span data-stu-id="47dd5-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="47dd5-113">Las ventajas de nombres seguros son:</span><span class="sxs-lookup"><span data-stu-id="47dd5-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="47dd5-114">El ensamblado se puede hacer referencia a y usar otros ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="47dd5-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="47dd5-115">El ensamblado se puede almacenar en caché de ensamblados Global (GAC).</span><span class="sxs-lookup"><span data-stu-id="47dd5-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="47dd5-116">El ensamblado se puede cargar en paralelo con otras versiones del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="47dd5-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="47dd5-117">Carga de ensamblados en paralelo se requieren habitualmente las aplicaciones con arquitecturas para complementos.</span><span class="sxs-lookup"><span data-stu-id="47dd5-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="47dd5-118">Crear seguro con el nombre de las bibliotecas de .NET</span><span class="sxs-lookup"><span data-stu-id="47dd5-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="47dd5-119">Se deben asignar un nombre seguro las bibliotecas .NET de código abierto.</span><span class="sxs-lookup"><span data-stu-id="47dd5-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="47dd5-120">Un ensamblado de nombres seguros garantiza la mayoría de los usuarios puede usarla y estricta ensamblado cargar solo afecta a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47dd5-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="47dd5-121">Esta guía es específica a las bibliotecas de .NET distribuidas públicamente, como bibliotecas de .NET publican en NuGet.org. Nombres seguros no es necesaria para la mayoría de las aplicaciones de .NET y no se deben realizar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47dd5-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="47dd5-122">**Considere la posibilidad de ✔️** seguro nombres a los ensamblados de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="47dd5-122">**✔️ CONSIDER** strong naming your library's assemblies.</span></span>

<span data-ttu-id="47dd5-123">**Considere la posibilidad de ✔️** comprobación de la clave utilizada para el nombre seguro en el sistema de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="47dd5-123">**✔️ CONSIDER** checking in the key used to strong name into your source control system.</span></span>

> <span data-ttu-id="47dd5-124">Una clave disponible públicamente permite a los programadores modificar y volver a compilar el código fuente de biblioteca con la misma clave.</span><span class="sxs-lookup"><span data-stu-id="47dd5-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47dd5-125">Cuando se desea una identidad de cifrado, [Authenticode](/windows-hardware/drivers/install/authenticode) y [firma del paquete NuGet](/nuget/create-packages/sign-a-package) se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="47dd5-125">When a cryptographic identity is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="47dd5-126">No se deben usar nombres seguros de consideraciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="47dd5-126">Strong naming should not be used for security considerations.</span></span>

<span data-ttu-id="47dd5-127">**Considere la posibilidad de ✔️** incrementar la versión de ensamblado en los cambios de versión principal solo para ayudar a los usuarios a reducir las redirecciones de enlace, y con qué frecuencia se actualizan.</span><span class="sxs-lookup"><span data-stu-id="47dd5-127">**✔️ CONSIDER** incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="47dd5-128">Obtenga más información sobre [control de versiones y la versión del ensamblado](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="47dd5-128">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="47dd5-129">**NO ❌** agregar, quitar o cambiar la clave de nomenclatura segura.</span><span class="sxs-lookup"><span data-stu-id="47dd5-129">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="47dd5-130">Modificar la clave de nomenclatura segura de un ensamblado cambia la identidad del ensamblado e interrumpe el código compilado que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="47dd5-130">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="47dd5-131">Para obtener más información, consulte [binario cambios importantes](./breaking-changes.md#binary-breaking-change).</span><span class="sxs-lookup"><span data-stu-id="47dd5-131">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="47dd5-132">**❌ NO** publicar versiones con nombre seguro y sin seguro-nombre de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="47dd5-132">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="47dd5-133">Por ejemplo, `Contoso.Api` y `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="47dd5-133">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="47dd5-134">Publicar dos bifurcaciones de paquetes en el ecosistema del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="47dd5-134">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="47dd5-135">Además, si una aplicación termina según ambos paquetes el desarrollador puede producirse conflictos de nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="47dd5-135">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="47dd5-136">En lo que se refiere .NET son tipos diferentes en distintos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="47dd5-136">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="47dd5-137">[Anterior](./cross-platform-targeting.md)
[Siguiente](./nuget.md)</span><span class="sxs-lookup"><span data-stu-id="47dd5-137">[Previous](./cross-platform-targeting.md)
[Next](./nuget.md)</span></span>

---
title: Nombres seguros y bibliotecas de .NET
description: Procedimientos recomendados para nombres de seguros de las bibliotecas de .NET.
ms.date: 10/16/2018
ms.openlocfilehash: db268093b07a2ece7cdb8329fd789b52da9c5c32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744535"
---
# <a name="strong-naming"></a><span data-ttu-id="07618-103">Nombres seguros</span><span class="sxs-lookup"><span data-stu-id="07618-103">Strong naming</span></span>

<span data-ttu-id="07618-104">Nombres seguros se refiere a firmar un ensamblado con una clave, generando un [ensamblado con nombre seguro](../assembly/strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="07618-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../assembly/strong-named.md).</span></span> <span data-ttu-id="07618-105">Una vez que un ensamblado tiene un nombre seguro, crea una identidad única en función del nombre y del número de versión del ensamblado y puede ayudar a evitar conflictos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07618-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="07618-106">El inconveniente de los nombres seguros es que .NET Framework en Windows habilita la carga estricta de ensamblados una vez que un ensamblado tiene un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="07618-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="07618-107">Una referencia de ensamblado con nombre seguro debe coincidir exactamente con la versión a la que un ensamblado hace referencia, obligando a los desarrolladores a [configurar redirecciones de enlace](../../framework/configure-apps/redirect-assembly-versions.md) cuando se usa el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="07618-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

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

<span data-ttu-id="07618-108">Cuando los desarrolladores de .NET se quejan de los nombres seguros, normalmente se quejan de la carga estricta de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="07618-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="07618-109">Afortunadamente, este problema está aislado en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07618-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="07618-110">.NET Core, Xamarin, UWP y la mayoría del resto de implementaciones de .NET no tienen carga estricta de ensamblados y quitan el principal inconveniente de los nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="07618-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="07618-111">Un aspecto importante de los nombres seguros es que son virales: un ensamblado con nombre seguro solamente pueden hacer referencia otros ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="07618-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="07618-112">Si la biblioteca no tiene un nombre seguro, es que se ha excluido a los desarrolladores que están creando una aplicación o biblioteca que necesita nombres seguros para usarla.</span><span class="sxs-lookup"><span data-stu-id="07618-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="07618-113">Las ventajas de los nombres seguros son:</span><span class="sxs-lookup"><span data-stu-id="07618-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="07618-114">Otros ensamblados con nombre seguro pueden hacer referencia al ensamblado y usarlo.</span><span class="sxs-lookup"><span data-stu-id="07618-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="07618-115">El ensamblado se puede almacenar en la memoria caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="07618-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="07618-116">El ensamblado se puede cargar en paralelo con otras versiones de dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07618-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="07618-117">Normalmente, las aplicaciones con arquitecturas de complemento requieren la carga de ensamblados en paralelo.</span><span class="sxs-lookup"><span data-stu-id="07618-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="07618-118">Creación de bibliotecas de .NET con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="07618-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="07618-119">Se deben asignar un nombre seguro a las bibliotecas de .NET de código abierto.</span><span class="sxs-lookup"><span data-stu-id="07618-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="07618-120">La asignación de un nombre seguro a un ensamblado garantiza que la mayoría de los usuarios pueden usarlo y la carga estricta del ensamblado solo afecta a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07618-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="07618-121">Esta guía es específica de las bibliotecas de .NET distribuidas públicamente, como las bibliotecas de .NET publicadas en NuGet.org. La mayoría de las aplicaciones .NET no necesitan nombres seguros y estos no se deben utilizar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="07618-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="07618-122">✔️ ES RECOMENDABLE usar nombres seguros en los ensamblados de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="07618-122">✔️ CONSIDER strong naming your library's assemblies.</span></span>

<span data-ttu-id="07618-123">✔️ ES RECOMENDABLE agregar la clave de nombres seguros al sistema de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="07618-123">✔️ CONSIDER adding the strong naming key to your source control system.</span></span>

> <span data-ttu-id="07618-124">Una clave disponible públicamente permite a los programadores modificar y volver a compilar el código fuente de la biblioteca con la misma clave.</span><span class="sxs-lookup"><span data-stu-id="07618-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>
>
> <span data-ttu-id="07618-125">No debería publicar la clave de nombres seguros si se ha utilizado en el pasado para conceder permisos especiales en [escenarios de confianza parcial](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span><span class="sxs-lookup"><span data-stu-id="07618-125">You shouldn't make the strong naming key public if it has been used in the past to give special permissions in [partial-trust scenarios](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span></span> <span data-ttu-id="07618-126">En caso contrario, podría poner en peligro los entornos existentes.</span><span class="sxs-lookup"><span data-stu-id="07618-126">Otherwise, you might compromise existing environments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07618-127">Cuando se desea la identidad del publicador del código, se recomiendan [Authenticode](/windows-hardware/drivers/install/authenticode) y la [firma de paquetes NuGet](/nuget/create-packages/sign-a-package).</span><span class="sxs-lookup"><span data-stu-id="07618-127">When the identity of the publisher of the code is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="07618-128">La seguridad de acceso del código (CAS) no debe usarse como una mitigación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="07618-128">Code Access Security (CAS) should not be used as a security mitigation.</span></span>

<span data-ttu-id="07618-129">✔️ ES RECOMENDABLE incrementar la versión de ensamblado solamente en los cambios de versión principal para ayudar a los usuarios a reducir las redirecciones de enlace y la frecuencia con la que se actualizan.</span><span class="sxs-lookup"><span data-stu-id="07618-129">✔️ CONSIDER incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="07618-130">Obtenga más información sobre el [control de versiones y la versión del ensamblado](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="07618-130">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="07618-131">❌ NO agregue, quite ni cambie la clave de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="07618-131">❌ DO NOT add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="07618-132">La modificación de la clave de nombre seguro de un ensamblado cambia la identidad de este e interrumpe el código compilado que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="07618-132">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="07618-133">Para más información, vea la información sobre [cambios importantes binarios](./breaking-changes.md#binary-breaking-change).</span><span class="sxs-lookup"><span data-stu-id="07618-133">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="07618-134">❌ NO publique versiones de la biblioteca tanto con nombre seguro como sin él.</span><span class="sxs-lookup"><span data-stu-id="07618-134">❌ DO NOT publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="07618-135">Por ejemplo, `Contoso.Api` y `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="07618-135">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="07618-136">La publicación de dos paquetes bifurca el ecosistema del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="07618-136">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="07618-137">Además, si una aplicación termina dependiendo de ambos paquetes, el desarrollador puede encontrar conflictos con el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="07618-137">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="07618-138">En lo que respecta a .NET, son tipos distintos en diferentes ensamblados.</span><span class="sxs-lookup"><span data-stu-id="07618-138">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="07618-139">[Anterior](cross-platform-targeting.md)
>[Siguiente](nuget.md)</span><span class="sxs-lookup"><span data-stu-id="07618-139">[Previous](cross-platform-targeting.md)
[Next](nuget.md)</span></span>

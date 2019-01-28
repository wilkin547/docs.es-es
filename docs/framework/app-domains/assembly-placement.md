---
title: Colocación de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2168c167c89f989f70a10d5832e70c93a8f90f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529900"
---
# <a name="assembly-placement"></a><span data-ttu-id="58e0d-102">Colocación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="58e0d-102">Assembly Placement</span></span>
<span data-ttu-id="58e0d-103">En la mayoría de las aplicaciones .NET Framework, los ensamblados que componen una aplicación se colocan en el directorio de la aplicación, en un subdirectorio de este último o en la caché global de ensamblados (si el ensamblado está compartido).</span><span class="sxs-lookup"><span data-stu-id="58e0d-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="58e0d-104">Para reemplazar la ubicación en la que Common Language Runtime busca un ensamblado, use el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="58e0d-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="58e0d-105">Si el ensamblado no tiene un nombre seguro, la ubicación especificada mediante el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) se limita al directorio de la aplicación o a un subdirectorio de este.</span><span class="sxs-lookup"><span data-stu-id="58e0d-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="58e0d-106">Si el ensamblado tiene un nombre seguro, el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) puede especificar cualquier ubicación en el equipo o en una red.</span><span class="sxs-lookup"><span data-stu-id="58e0d-106">If the assembly has a strong name, the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="58e0d-107">Se aplican reglas similares a la búsqueda de ensamblados cuando se trabaja con código no administrado o aplicaciones de interoperabilidad COM: si el ensamblado va a compartirse entre varias aplicaciones, debe instalarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="58e0d-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="58e0d-108">Los ensamblados que se utilizan con código no administrado deben exportarse como biblioteca de tipos y registrarse.</span><span class="sxs-lookup"><span data-stu-id="58e0d-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="58e0d-109">Los ensamblados utilizados por la interoperabilidad COM deben registrarse en el catálogo, aunque, en algunos casos, este registro es automático.</span><span class="sxs-lookup"><span data-stu-id="58e0d-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e0d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="58e0d-110">See also</span></span>
- [<span data-ttu-id="58e0d-111">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="58e0d-111">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="58e0d-112">Configurar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="58e0d-112">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="58e0d-113">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="58e0d-113">Interoperating with unmanaged code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="58e0d-114">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="58e0d-114">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)

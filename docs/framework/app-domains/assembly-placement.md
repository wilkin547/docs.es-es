---
title: "Colocación de ensamblados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f5f80649e214583dae52ed8ec7933b77bf72fca5
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="assembly-placement"></a><span data-ttu-id="fa6a6-102">Colocación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="fa6a6-102">Assembly Placement</span></span>
<span data-ttu-id="fa6a6-103">En la mayoría de las aplicaciones .NET Framework, los ensamblados que componen una aplicación se colocan en el directorio de la aplicación, en un subdirectorio de este último o en la caché global de ensamblados (si el ensamblado está compartido).</span><span class="sxs-lookup"><span data-stu-id="fa6a6-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="fa6a6-104">Para reemplazar la ubicación en la que Common Language Runtime busca un ensamblado, use el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa6a6-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="fa6a6-105">Si el ensamblado no tiene un nombre seguro, la ubicación especificada mediante el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) se limita al directorio de la aplicación o a un subdirectorio de este.</span><span class="sxs-lookup"><span data-stu-id="fa6a6-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="fa6a6-106">Si el ensamblado tiene un nombre seguro, el [elemento \<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) puede especificar cualquier ubicación en el equipo o en una red.</span><span class="sxs-lookup"><span data-stu-id="fa6a6-106">If the assembly has a strong name, the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="fa6a6-107">Se aplican reglas similares a la búsqueda de ensamblados cuando se trabaja con código no administrado o aplicaciones de interoperabilidad COM: si el ensamblado va a compartirse entre varias aplicaciones, debe instalarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fa6a6-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="fa6a6-108">Los ensamblados que se utilizan con código no administrado deben exportarse como biblioteca de tipos y registrarse.</span><span class="sxs-lookup"><span data-stu-id="fa6a6-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="fa6a6-109">Los ensamblados utilizados por la interoperabilidad COM deben registrarse en el catálogo, aunque, en algunos casos, este registro es automático.</span><span class="sxs-lookup"><span data-stu-id="fa6a6-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6a6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa6a6-110">See Also</span></span>  
 <span data-ttu-id="fa6a6-111">[Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="fa6a6-111">[How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span></span>  
 <span data-ttu-id="fa6a6-112">[Configurar aplicaciones](../../../docs/framework/configure-apps/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa6a6-112">[Configuring Apps](../../../docs/framework/configure-apps/index.md) </span></span>  
 <span data-ttu-id="fa6a6-113">[Interoperabilidad COM avanzada](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span><span class="sxs-lookup"><span data-stu-id="fa6a6-113">[Advanced COM Interoperability](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span></span>  
 [<span data-ttu-id="fa6a6-114">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="fa6a6-114">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)


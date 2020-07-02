---
title: Colocación de ensamblados
description: Revise las directrices para la colocación de ensamblados .NET en directorios (por ejemplo, en la caché global de ensamblados o en el directorio o subdirectorio de la aplicación).
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
ms.openlocfilehash: 3106f6f01229057725cbc2e8e689a4e2247f95e6
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104962"
---
# <a name="assembly-placement"></a><span data-ttu-id="4a07a-103">Colocación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="4a07a-103">Assembly Placement</span></span>
<span data-ttu-id="4a07a-104">En la mayoría de las aplicaciones .NET Framework, los ensamblados que componen una aplicación se colocan en el directorio de la aplicación, en un subdirectorio de este último o en la caché global de ensamblados (si el ensamblado está compartido).</span><span class="sxs-lookup"><span data-stu-id="4a07a-104">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="4a07a-105">Para reemplazar la ubicación en la que Common Language Runtime busca un ensamblado, use el [elemento \<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4a07a-105">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="4a07a-106">Si el ensamblado no tiene un nombre seguro, la ubicación especificada mediante el [elemento \<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) se limita al directorio de la aplicación o a un subdirectorio de este.</span><span class="sxs-lookup"><span data-stu-id="4a07a-106">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="4a07a-107">Si el ensamblado tiene un nombre seguro, el [elemento \<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md) puede especificar cualquier ubicación en el equipo o en una red.</span><span class="sxs-lookup"><span data-stu-id="4a07a-107">If the assembly has a strong name, the [\<codeBase> Element](../configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="4a07a-108">Se aplican reglas similares a la búsqueda de ensamblados cuando se trabaja con código no administrado o aplicaciones de interoperabilidad COM: si el ensamblado va a compartirse entre varias aplicaciones, debe instalarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4a07a-108">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="4a07a-109">Los ensamblados que se utilizan con código no administrado deben exportarse como biblioteca de tipos y registrarse.</span><span class="sxs-lookup"><span data-stu-id="4a07a-109">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="4a07a-110">Los ensamblados utilizados por la interoperabilidad COM deben registrarse en el catálogo, aunque, en algunos casos, este registro es automático.</span><span class="sxs-lookup"><span data-stu-id="4a07a-110">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a07a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a07a-111">See also</span></span>

- [<span data-ttu-id="4a07a-112">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="4a07a-112">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="4a07a-113">Configurar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4a07a-113">Configuring Apps</span></span>](../configure-apps/index.md)
- [<span data-ttu-id="4a07a-114">Interoperar con código no administrado</span><span class="sxs-lookup"><span data-stu-id="4a07a-114">Interoperating with unmanaged code</span></span>](../interop/index.md)
- [<span data-ttu-id="4a07a-115">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="4a07a-115">Assemblies in .NET</span></span>](index.md)

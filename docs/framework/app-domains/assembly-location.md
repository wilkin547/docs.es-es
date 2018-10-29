---
title: Ubicación del ensamblado
ms.date: 03/30/2017
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19c4b030e8b44bed5377827d016127b4a574f5ee
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "50183755"
---
# <a name="assembly-location"></a><span data-ttu-id="961c3-102">Ubicación del ensamblado</span><span class="sxs-lookup"><span data-stu-id="961c3-102">Assembly Location</span></span>
<span data-ttu-id="961c3-103">La ubicación de un ensamblado determina si Common Language Runtime lo encontrará cuando se haga referencia a él y también puede determinar si el ensamblado se puede compartir con otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="961c3-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="961c3-104">Puede implementar un ensamblado en las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="961c3-104">You can deploy an assembly in the following locations:</span></span>  
  
-   <span data-ttu-id="961c3-105">El directorio de la aplicación o subdirectorios de este.</span><span class="sxs-lookup"><span data-stu-id="961c3-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="961c3-106">Esta es la ubicación más común para implementar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="961c3-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="961c3-107">Los subdirectorios del directorio raíz de la aplicación pueden basarse en un idioma o referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="961c3-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="961c3-108">Si un ensamblado tiene información en el atributo de referencia cultural, debe estar en un subdirectorio bajo el directorio de la aplicación con el nombre de esa referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="961c3-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
-   <span data-ttu-id="961c3-109">La caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="961c3-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="961c3-110">Se trata de una caché de código del equipo que se instala donde está instalado Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="961c3-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="961c3-111">En la mayoría de los casos, si se piensa compartir un ensamblado entre varias aplicaciones, debe implementarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="961c3-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="961c3-112">Un servidor HTTP.</span><span class="sxs-lookup"><span data-stu-id="961c3-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="961c3-113">Un ensamblado implementado en un servidor HTTP debe tener un nombre seguro. Debe apuntar al ensamblado en la sección de código base del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="961c3-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961c3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="961c3-114">See Also</span></span>  
- [<span data-ttu-id="961c3-115">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="961c3-115">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
- [<span data-ttu-id="961c3-116">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="961c3-116">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
- [<span data-ttu-id="961c3-117">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="961c3-117">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
- [<span data-ttu-id="961c3-118">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="961c3-118">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

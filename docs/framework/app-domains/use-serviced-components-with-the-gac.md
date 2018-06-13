---
title: Utilizar componentes con servicio junto con la memoria caché global de ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 703e71661c7a679b85e60726f53b275fce1a4d6a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753357"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="04392-102">Utilizar componentes con servicio junto con la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="04392-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="04392-103">Los componentes con servicio (componentes COM+ de código administrado) deben colocarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="04392-103">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="04392-104">En algunos escenarios, Common Language Runtime y los Servicios COM+ pueden controlar los componentes con servicio que no están en la caché global de ensamblados; en otros escenarios no pueden.</span><span class="sxs-lookup"><span data-stu-id="04392-104">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="04392-105">Estos escenarios ilustran lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04392-105">The following scenarios illustrate this:</span></span>  
  
-   <span data-ttu-id="04392-106">En el caso de los componentes con servicio en una aplicación de servidor COM+, el ensamblado que contiene los componentes debe estar en la caché global de ensamblados, ya que Dllhost.exe no se ejecuta en el mismo directorio que contiene los componentes con servicio.</span><span class="sxs-lookup"><span data-stu-id="04392-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
-   <span data-ttu-id="04392-107">Para los componentes con servicio en una aplicación de COM+ Library, Common Language Runtime y COM+ Services pueden resolver la referencia al ensamblado que contiene los componentes buscando en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="04392-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="04392-108">En este caso, el ensamblado no tiene que estar en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="04392-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="04392-109">Para los componentes con servicio en una aplicación ASP.NET, la situación es distinta.</span><span class="sxs-lookup"><span data-stu-id="04392-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="04392-110">Si coloca el ensamblado que contiene los componentes con servicio en el directorio bin de la base de la aplicación y utiliza el registro a petición, se copiará una instantánea del ensamblado en la caché de descarga porque ASP.NET aprovecha las funcionalidades de copia de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="04392-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04392-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="04392-111">See Also</span></span>  
 [<span data-ttu-id="04392-112">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="04392-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="04392-113">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="04392-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)

---
title: Optimización de hospedaje web compartido
ms.date: 03/30/2017
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
ms.openlocfilehash: abab4ac451a70fbc81ac6d7c9da6f8d0123287a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669034"
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="0799a-102">Optimización de hospedaje web compartido</span><span class="sxs-lookup"><span data-stu-id="0799a-102">Optimization for Shared Web Hosting</span></span>

<span data-ttu-id="0799a-103">Si es el administrador de un servidor compartido que hospeda varios sitios web pequeños, puede optimizar el rendimiento y aumentar la capacidad del sitio si agrega la siguiente configuración `gcTrimCommitOnLowMemory` al nodo `runtime` en el archivo Aspnet.config del directorio de .NET:</span><span class="sxs-lookup"><span data-stu-id="0799a-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
> <span data-ttu-id="0799a-104">Esta configuración solo se recomienda para escenarios de hospedaje web compartido.</span><span class="sxs-lookup"><span data-stu-id="0799a-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="0799a-105">Dado que el recolector de elementos no utilizados conserva la memoria para asignaciones futuras, su espacio confirmado puede ser mayor que el estrictamente necesario.</span><span class="sxs-lookup"><span data-stu-id="0799a-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="0799a-106">Puede reducir este espacio para dar cabida a las veces en que haya una carga pesada en la memoria del sistema.</span><span class="sxs-lookup"><span data-stu-id="0799a-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="0799a-107">Reducir este espacio confirmado mejora el rendimiento y amplía la capacidad de hospedar varios sitios.</span><span class="sxs-lookup"><span data-stu-id="0799a-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="0799a-108">Cuando la opción `gcTrimCommitOnLowMemory` está habilitada, el recolector de elementos no utilizados evalúa la carga de memoria del sistema y entra en un modo de reducción cuando la carga alcanza el 90 %.</span><span class="sxs-lookup"><span data-stu-id="0799a-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="0799a-109">El modo de reducción se mantiene hasta que la carga desciende por debajo del 85 %.</span><span class="sxs-lookup"><span data-stu-id="0799a-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="0799a-110">Cuando las condiciones lo permiten, el recolector de elementos no utilizados puede decidir que la configuración `gcTrimCommitOnLowMemory` ya no ayudará a la aplicación actual y la ignora.</span><span class="sxs-lookup"><span data-stu-id="0799a-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0799a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0799a-111">Example</span></span>  

 <span data-ttu-id="0799a-112">El siguiente fragmento XML muestra cómo habilitar la configuración `gcTrimCommitOnLowMemory`.</span><span class="sxs-lookup"><span data-stu-id="0799a-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="0799a-113">Los puntos suspensivos indican otros valores que podrían estar en el nodo `runtime`.</span><span class="sxs-lookup"><span data-stu-id="0799a-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0799a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0799a-114">See also</span></span>

- [<span data-ttu-id="0799a-115">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="0799a-115">Garbage Collection</span></span>](index.md)

---
title: "Optimización de hospedaje web compartido"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="15612-102">Optimización de hospedaje web compartido</span><span class="sxs-lookup"><span data-stu-id="15612-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="15612-103">Si usted es el Administrador de un servidor compartido que hospeda varios sitios Web pequeños, puede optimizar el rendimiento y aumentar la capacidad del sitio debe agregar lo siguiente `gcTrimCommitOnLowMemory` si se establece en el `runtime` nodo en el archivo Aspnet.config en .NET directorio:</span><span class="sxs-lookup"><span data-stu-id="15612-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="15612-104">Esta configuración solo se recomienda para Web compartida de escenarios de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="15612-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="15612-105">Dado que el recolector de elementos no utilizados conserva la memoria para asignaciones futuras, su espacio confirmado puede ser mayor que los estrictamente necesarios.</span><span class="sxs-lookup"><span data-stu-id="15612-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="15612-106">Puede reducir este espacio para dar cabida a veces cuando hay una carga pesada en memoria del sistema.</span><span class="sxs-lookup"><span data-stu-id="15612-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="15612-107">Reducir este espacio confirmado mejora el rendimiento y amplía la capacidad de hospedar varios sitios.</span><span class="sxs-lookup"><span data-stu-id="15612-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="15612-108">Cuando el `gcTrimCommitOnLowMemory` opción está habilitada, el recolector de elementos no utilizados evalúa la carga de memoria del sistema y entra en un modo de reducción cuando la carga alcanza el 90%.</span><span class="sxs-lookup"><span data-stu-id="15612-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="15612-109">El modo de reducción mantiene hasta que la carga desciende por debajo del 85%.</span><span class="sxs-lookup"><span data-stu-id="15612-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="15612-110">Cuando las condiciones lo permiten, el recolector de elementos no utilizados puede decidir que la `gcTrimCommitOnLowMemory` configuración no ayudan a la aplicación actual y omitirla.</span><span class="sxs-lookup"><span data-stu-id="15612-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15612-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15612-111">Example</span></span>  
 <span data-ttu-id="15612-112">El siguiente fragmento XML muestra cómo habilitar el `gcTrimCommitOnLowMemory` configuración.</span><span class="sxs-lookup"><span data-stu-id="15612-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="15612-113">Los puntos suspensivos indican otros valores que podrían estar en el `runtime` nodo.</span><span class="sxs-lookup"><span data-stu-id="15612-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="15612-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="15612-114">See Also</span></span>  
 [<span data-ttu-id="15612-115">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="15612-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)

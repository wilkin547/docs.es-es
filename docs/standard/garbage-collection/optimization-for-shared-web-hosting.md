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
# <a name="optimization-for-shared-web-hosting"></a>Optimización de hospedaje web compartido
Si usted es el Administrador de un servidor compartido que hospeda varios sitios Web pequeños, puede optimizar el rendimiento y aumentar la capacidad del sitio debe agregar lo siguiente `gcTrimCommitOnLowMemory` si se establece en el `runtime` nodo en el archivo Aspnet.config en .NET directorio:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Esta configuración solo se recomienda para Web compartida de escenarios de hospedaje.  
  
 Dado que el recolector de elementos no utilizados conserva la memoria para asignaciones futuras, su espacio confirmado puede ser mayor que los estrictamente necesarios. Puede reducir este espacio para dar cabida a veces cuando hay una carga pesada en memoria del sistema. Reducir este espacio confirmado mejora el rendimiento y amplía la capacidad de hospedar varios sitios.  
  
 Cuando el `gcTrimCommitOnLowMemory` opción está habilitada, el recolector de elementos no utilizados evalúa la carga de memoria del sistema y entra en un modo de reducción cuando la carga alcanza el 90%. El modo de reducción mantiene hasta que la carga desciende por debajo del 85%.  
  
 Cuando las condiciones lo permiten, el recolector de elementos no utilizados puede decidir que la `gcTrimCommitOnLowMemory` configuración no ayudan a la aplicación actual y omitirla.  
  
## <a name="example"></a>Ejemplo  
 El siguiente fragmento XML muestra cómo habilitar el `gcTrimCommitOnLowMemory` configuración. Los puntos suspensivos indican otros valores que podrían estar en el `runtime` nodo.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Recolección de elementos no utilizados](../../../docs/standard/garbage-collection/index.md)

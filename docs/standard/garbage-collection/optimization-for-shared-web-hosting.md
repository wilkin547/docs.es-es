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
# <a name="optimization-for-shared-web-hosting"></a>Optimización de hospedaje web compartido

Si es el administrador de un servidor compartido que hospeda varios sitios web pequeños, puede optimizar el rendimiento y aumentar la capacidad del sitio si agrega la siguiente configuración `gcTrimCommitOnLowMemory` al nodo `runtime` en el archivo Aspnet.config del directorio de .NET:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
> Esta configuración solo se recomienda para escenarios de hospedaje web compartido.  
  
 Dado que el recolector de elementos no utilizados conserva la memoria para asignaciones futuras, su espacio confirmado puede ser mayor que el estrictamente necesario. Puede reducir este espacio para dar cabida a las veces en que haya una carga pesada en la memoria del sistema. Reducir este espacio confirmado mejora el rendimiento y amplía la capacidad de hospedar varios sitios.  
  
 Cuando la opción `gcTrimCommitOnLowMemory` está habilitada, el recolector de elementos no utilizados evalúa la carga de memoria del sistema y entra en un modo de reducción cuando la carga alcanza el 90 %. El modo de reducción se mantiene hasta que la carga desciende por debajo del 85 %.  
  
 Cuando las condiciones lo permiten, el recolector de elementos no utilizados puede decidir que la configuración `gcTrimCommitOnLowMemory` ya no ayudará a la aplicación actual y la ignora.  
  
## <a name="example"></a>Ejemplo  

 El siguiente fragmento XML muestra cómo habilitar la configuración `gcTrimCommitOnLowMemory`. Los puntos suspensivos indican otros valores que podrían estar en el nodo `runtime`.  
  
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

- [Recolección de elementos no utilizados](index.md)

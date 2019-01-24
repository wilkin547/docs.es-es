---
title: Eventos ETW de contención
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90beb1487581ff4c031d6f10fb613430207dc026
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575572"
---
# <a name="contention-etw-events"></a>Eventos ETW de contención
Los eventos de contención se generan cuando el tiempo de ejecución usa contención de bloqueos <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativos. La contención se produce cuando un subproceso espera un bloqueo mientras otro posee el bloqueo.  
  
 En la tabla siguiente se muestra la palabra clave bajo la que se generan los eventos de contención y el nivel de los eventos. (Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ContentionKeyword` (0x4000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|81|Se inicia la contención. Este evento no incluye la cantidad de tiempo de giro antes de que un subproceso comience a esperar para adquirir un bloqueo; solo se genera cuando el subproceso espera para adquirir un bloqueo.|  
|`ContentionStop`|81|Finaliza la contención.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|Marcas|win:UInt8|0 para administrado; 1 para nativo.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR.|  
  
## <a name="see-also"></a>Vea también
- [CLR ETW Events (Eventos ETW de CLR)](../../../docs/framework/performance/clr-etw-events.md)

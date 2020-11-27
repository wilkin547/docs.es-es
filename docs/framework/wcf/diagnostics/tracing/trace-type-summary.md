---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e8d222d6f093f5db3bd620194bfde7edd4b998a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259250"
---
# <a name="trace-type-summary"></a>Resumen del tipo de seguimiento

[Niveles de origen](xref:System.Diagnostics.SourceLevels) define varios niveles de seguimiento: crítico, error, ADVERTENCIA, información y detallado, así como una descripción de la `ActivityTracing` marca, que alterna la salida del límite de seguimiento y los eventos de transferencia de actividad.  
  
 También puede revisar <xref:System.Diagnostics.TraceEventType> los tipos de seguimientos que se pueden emitir desde <xref:System.Diagnostics> .  
  
 La tabla siguiente enumera los más importantes.  
  
|Tipo de traza|Descripción|  
|----------------|-----------------|  
|Crítico|Error irrecuperable o bloqueo de la aplicación.|  
|Error|Error recuperable.|  
|Advertencia|Mensaje informativo.|  
|Información|Problema no crítico.|  
|Verbose|Traza de depuración.|  
|Inicio|Inicio de una unidad lógica de procesamiento.|  
|Suspender|Suspensión de una unidad lógica de procesamiento.|  
|Reanudar|Reanudación de una unidad lógica de procesamiento.|  
|Stop|Detención de una unidad lógica de procesamiento.|  
|Transferencia|Cambio de la identidad de correlación.|  
  
 Una actividad se define como una combinación de los tipos de trazas anteriores.  
  
 La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local (origen de la traza),  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Esto significa que una actividad debe satisfacer las condiciones siguientes.  
  
- Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente  
  
- Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación  
  
- No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan  
  
- Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores  
  
 La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,  
  
`R+`  
  
 en la que R es la expresión regular para una actividad en el ámbito local. Esto se traduce en,  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`

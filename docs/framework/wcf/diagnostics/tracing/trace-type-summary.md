---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8ed6dceb19caa52f928f285064c60337e3f15a87
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674838"
---
# <a name="trace-type-summary"></a>Resumen del tipo de seguimiento
[Niveles](xref:System.Diagnostics.SourceLevels) de origen define varios niveles de seguimiento: Crítico, Error, Advertencia, Información `ActivityTracing` y Detallado, así como proporciona una descripción de la marca, que alterna la salida de los eventos de transferencia de actividad y límite de seguimiento.  
  
 También puede <xref:System.Diagnostics.TraceEventType> revisar los tipos de seguimientos <xref:System.Diagnostics>que se pueden emitir desde .  
  
 La tabla siguiente enumera los más importantes.  
  
|Tipo de traza|Descripción|  
|----------------|-----------------|  
|Crítico|Error irrecuperable o bloqueo de la aplicación.|  
|Error|Error recuperable.|  
|Advertencia|Mensaje informativo.|  
|Information|Problema no crítico.|  
|Verbose|Traza de depuración.|  
|Start|Inicio de una unidad lógica de procesamiento.|  
|Suspender|Suspensión de una unidad lógica de procesamiento.|  
|Reanudación|Reanudación de una unidad lógica de procesamiento.|  
|Stop|Detención de una unidad lógica de procesamiento.|  
|Transferir|Cambio de la identidad de correlación.|  
  
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

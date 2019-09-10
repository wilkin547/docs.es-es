---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8f54f71ef63338708a29fac5557c7c7e8f257f58
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856012"
---
# <a name="trace-type-summary"></a>Resumen del tipo de seguimiento
[Niveles de origen](https://go.microsoft.com/fwlink/?LinkID=94943) define varios niveles de seguimiento: Crítico, error, ADVERTENCIA, información y detallado, además de proporcionar una descripción de la `ActivityTracing` marca, que alterna la salida del límite de seguimiento y los eventos de transferencia de actividad.  
  
 También puede revisar [TraceEventType](https://go.microsoft.com/fwlink/?LinkId=95169) para ver los tipos de seguimientos que se pueden emitir <xref:System.Diagnostics>desde.  
  
 La tabla siguiente enumera los más importantes.  
  
|Tipo de traza|DESCRIPCIÓN|  
|----------------|-----------------|  
|Crítico|Error irrecuperable o bloqueo de la aplicación.|  
|Error|Error recuperable.|  
|Advertencia|Mensaje informativo.|  
|Información|Problema no crítico.|  
|Detallado|Traza de depuración.|  
|Iniciar|Inicio de una unidad lógica de procesamiento.|  
|Suspender|Suspensión de una unidad lógica de procesamiento.|  
|Reanudar|Reanudación de una unidad lógica de procesamiento.|  
|Detener|Detención de una unidad lógica de procesamiento.|  
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

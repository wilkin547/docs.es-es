---
title: Resumen del tipo de seguimiento
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e3bc66753dd44e1dc4c7417caf593820300f69a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486047"
---
# <a name="trace-type-summary"></a>Resumen del tipo de seguimiento
[Niveles de origen](http://go.microsoft.com/fwlink/?LinkID=94943) define distintos niveles de seguimiento: crítico, Error, advertencia, información y detallado, así, proporciona una descripción de la `ActivityTracing` marca, que alterna el resultado de seguimiento de eventos de transferencia de límite y la actividad.  
  
 También puede revisar [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) para los tipos de seguimientos que se pueden emitir desde <xref:System.Diagnostics>.  
  
 La tabla siguiente enumera los más importantes.  
  
|Tipo de traza|Descripción|  
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
  
-   Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente  
  
-   Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación  
  
-   No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan  
  
-   Puede tener cuantas trazas crítico/error/advertencia/información/detalles/transferencia, siempre y cuando se cumplan las condiciones anteriores  
  
 La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,  
  
```  
R+   
```  
  
 en la que R es la expresión regular para una actividad en el ámbito local. Esto se traduce en,  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```

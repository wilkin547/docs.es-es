---
title: "Resumen del tipo de seguimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Resumen del tipo de seguimiento
En [Source Levels](http://go.microsoft.com/fwlink/?LinkID=94943) se definen los distintos niveles de seguimiento: crítico, error, advertencia, información y detallado; además, se proporciona una descripción de la marca `ActivityTracing`, que alterna el resultado de los eventos de límite de seguimiento y de transferencia de actividad.  
  
 También puede consultar [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) para ver los tipos de rastros que se pueden emitir desde <xref:System.Diagnostics>.  
  
 La tabla siguiente enumera los más importantes.  
  
|Tipo de traza|Descripción|  
|-------------------|-----------------|  
|Crítico|Error irrecuperable o bloqueo de la aplicación.|  
|Error|Error recuperable.|  
|Advertencia|Mensaje informativo.|  
|Información|Problema no crítico.|  
|Detallado|Traza de depuración.|  
|Iniciar|Inicio de una unidad lógica de procesamiento.|  
|Suspender|Suspensión de una unidad lógica de procesamiento.|  
|Resume|Reanudación de una unidad lógica de procesamiento.|  
|Detener|Detención de una unidad lógica de procesamiento.|  
|Transferir|Cambio de la identidad de correlación.|  
  
 Una actividad se define como una combinación de los tipos de trazas anteriores.  
  
 La siguiente expresión se utiliza habitualmente para definir una actividad ideal en un ámbito local \(origen de la traza\),  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 Esto significa que una actividad debe satisfacer las condiciones siguientes.  
  
-   Debe iniciarse y detenerse por trazas de inicio y detención, respectivamente  
  
-   Debe tener una traza de transferencia que preceda inmediatamente a una traza de suspensión o reanudación  
  
-   No debe presentar traza alguna entre las trazas de suspensión y reanudación, en caso de que éstas existan  
  
-   Puede tener cuantas trazas crítico\/error\/advertencia\/información\/detalles\/transferencia, siempre y cuando se cumplan las condiciones anteriores  
  
 La siguiente expresión se utiliza habitualmente para definir una actividad ideal en el ámbito global,  
  
```  
R+   
```  
  
 en la que R es la expresión regular para una actividad en el ámbito local.  Esto se traduce en,  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
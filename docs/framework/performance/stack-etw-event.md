---
title: "Stack ETW Event | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "stack event [.NET Framework]"
  - "ETW, stack event (CLR)"
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Stack ETW Event
El evento de pila se debe utilizar en combinación con otros eventos para generar trazas de pila una vez generado un evento.  Se registra cuando el proveedor en tiempo de ejecución está habilitado.  Éste es un evento muy frecuente, porque se produce siempre que produce otro evento en tiempo de ejecución.  Por esta razón, recomendamos utilizar este evento con precaución.  
  
 En la siguiente tabla se muestran la palabra clave y el nivel. \(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)\).  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`StackKeyword` \(0x40000000\)|LogAlways\(0\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Identificador de evento|Se genera cuando|  
|------------|-----------------------------|----------------------|  
|`CLRStackWalk`|82|En combinación con otros eventos para generar trazas de pila tras un evento.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|ClrInstanceID|win:Uint16|Identificador único en tiempo de ejecución.|  
|Reserved1|win:UInt8|Reservado.|  
|Reserved2|win:UInt8|Reservado.|  
|FrameCount|win:UInt32|Número de marcos en el seguimiento de pila.|  
|Pila|win:Pointer|Columnas de punteros de instrucción.|  
  
## Vea también  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)
---
title: "Exception Thrown_V1 ETW Event | Microsoft Docs"
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
  - "ExceptionThrown_V1 event [.NET Framework]"
  - "ETW, ExceptionThrown_V1 event (CLR)"
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# Exception Thrown_V1 ETW Event
Este evento captura información acerca de las excepciones que se producen.  
  
 En la siguiente tabla se muestran la palabra clave con la que se genera el evento y el nivel del evento. \(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)\).  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`ExceptionKeyword` \(0x8000\)|Advertencia \(2\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Identificador de evento|Se genera cuando|  
|------------|-----------------------------|----------------------|  
|`ExceptionThrown_V1`|80|Se produce una excepción administrada.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|Tipo de excepción|win:UnicodeString|El tipo de la excepción; por ejemplo, `System.NullReferenceException`.|  
|Mensaje de la excepción|win:UnicodeString|El mensaje de excepción real.|  
|EIPCodeThrow|win:Pointer|Puntero de instrucción donde se ha producido la excepción.|  
|ExceptionHR|win:UInt32|Excepción [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException \(vea [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) en la documentación de Visual Basic\).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException \(indica que el estado del proceso está dañado; consulte [Administrar excepciones de estado dañado](http://go.microsoft.com/fwlink/?LinkId=179681) MSDN\).<br /><br /> 0x10: IsCLSCompliant \(una excepción que deriva de <xref:System.Exception> es conforme a CLS; de lo contrario, no es conforme a CLS\).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## Vea también  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)
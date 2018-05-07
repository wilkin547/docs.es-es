---
title: Evento ETW de excepción Thrown_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dafa5846f779276ab81e8e30e7c7a50b9fbff853
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="exception-thrownv1-etw-event"></a>Evento ETW de excepción Thrown_V1
Este evento captura información sobre las excepciones que se generan.  
  
 En la tabla siguiente se muestra la palabra clave bajo la que se genera el evento, y el nivel del evento. (Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Advertencia (2)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Se genera una excepción administrada.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|Tipo de excepción|win:UnicodeString|Tipo de la excepción; por ejemplo, `System.NullReferenceException`.|  
|Mensaje de la excepción|win:UnicodeString|Mensaje actual de la excepción.|  
|EIPCodeThrow|win:Pointer|Puntero de instrucción donde se ha producido la excepción.|  
|ExceptionHR|win:UInt32|Excepción [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (vea [Eventos ETW de CLR](../../../docs/framework/performance/clr-etw-events.md) en la documentación de Visual Basic).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (indica que el estado del proceso está dañado; vea [Control de excepciones de estado dañadas](http://go.microsoft.com/fwlink/?LinkId=179681) en MSDN).<br /><br /> 0x10: IsCLSCompliant (una excepción que deriva de <xref:System.Exception> es conforme a CLS; de lo contrario, no es conforme a CLS).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vea también  
 [CLR ETW Events (Eventos ETW de CLR)](../../../docs/framework/performance/clr-etw-events.md)

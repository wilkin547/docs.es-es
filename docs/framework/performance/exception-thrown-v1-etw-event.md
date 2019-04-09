---
title: Evento ETW de excepción Thrown_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd322d25d91bb277a4c817594c968c28a6d61d68
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136141"
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
|ExceptionHR|win:UInt32|Excepción [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (vea [eventos ETW de CLR](../../../docs/framework/performance/clr-etw-events.md) en la documentación de Visual Basic).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (indica que el estado del proceso está dañado; vea [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) en MSDN).<br /><br /> 0x10: IsCLSCompliant (una excepción que se deriva de <xref:System.Exception> es conforme a CLS; en caso contrario, no es conforme a CLS).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vea también

- [Eventos ETW de CLR](../../../docs/framework/performance/clr-etw-events.md)

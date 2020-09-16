---
title: Evento ETW de excepción Thrown_V1
description: Vea información detallada sobre el evento ETW ExceptionThrown_V1. Los datos de eventos, como los nombres de campo, los tipos de datos y las descripciones, se proporcionan para las excepciones producidas.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f4ae277b5dfb09d2676755fec2208b63906ead84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554676"
---
# <a name="exception-thrown_v1-etw-event"></a>Evento ETW de excepción Thrown_V1
Este evento captura información sobre las excepciones que se generan.  
  
 En la tabla siguiente se muestra la palabra clave bajo la que se genera el evento, y el nivel del evento. (Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Advertencia (2)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Se genera una excepción administrada.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|Tipo de excepción|win:UnicodeString|Tipo de la excepción; por ejemplo, `System.NullReferenceException`.|  
|Mensaje de la excepción|win:UnicodeString|Mensaje actual de la excepción.|  
|EIPCodeThrow|win:Pointer|Puntero de instrucción donde se ha producido la excepción.|  
|ExceptionHR|win:UInt32|Excepción [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (vea [Eventos ETW de CLR](clr-etw-events.md) en la documentación de Visual Basic).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (indica que el estado del proceso está dañado; consulte [control de excepciones de estado dañadas](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).<br /><br /> 0x10: IsCLSCompliant (una excepción que deriva de <xref:System.Exception> es conforme a CLS; de lo contrario, no es conforme a CLS).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vea también

- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)

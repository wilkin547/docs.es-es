---
title: Eventos ETW de interoperabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5db68cdce0db4f8f4d85e9d1dd03720bf235d865
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974934"
---
# <a name="interop-etw-events"></a>Eventos ETW de interoperabilidad
Los eventos de interoperabilidad capturan información sobre el almacenamiento en caché y la generación de código auxiliar del lenguaje intermedio (MSIL) de Microsoft.  

## <a name="ilstubgenerated-event"></a>Evento ILStubGenerated

En la tabla siguiente se muestra la palabra clave y el nivel. (Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0 x 2000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|88|Se generó código auxiliar MSIL.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Identificador del módulo.|  
|StubMethodID|win:UInt64|Identificador del método de código auxiliar.|  
|StubFlags|win:UInt64|Marcas para el código auxiliar:<br /><br /> 0x1 - Interoperabilidad inversa.<br /><br /> 0x2 - Interoperabilidad COM.<br /><br /> 0x4 - Código auxiliar generado por NGen.exe.<br /><br /> 0x8 - Delegado.<br /><br /> 0x10-argumento variable.<br /><br /> 0x20 - Destinatario no administrado.|  
|ManagedInteropMethodToken|win:UInt32|Token del método de interoperabilidad administrado.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Espacio de nombres del método de interoperabilidad administrado.|  
|ManagedInteropMethodName|win:UnicodeString|Nombre del método de interoperabilidad administrado.|  
|ManagedInteropMethodSignature|win:UnicodeString|Firma del método de interoperabilidad administrado.|  
|NativeMethodSignature|win:UnicodeString|Firma del método nativo.|  
|StubMethodSignature|win:UnicodeString|Firma del método de código auxiliar.|  
|StubMethodILCode|win:UnicodeString|Código MSIL para el método de código auxiliar.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="ilstubcachehit-event"></a>Evento ILStubCacheHit  

En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0 x 2000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|89|Se tuvo acceso a la memoria caché MSIL.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Identificador del módulo.|  
|StubMethodID|win:UInt64|Identificador del método de código auxiliar.|  
|ManagedInteropMethodToken|win:UInt32|Token del método de interoperabilidad administrado.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Espacio de nombres del método de interoperabilidad administrado.|  
|ManagedInteropMethodName|win:UnicodeString|Nombre del método de interoperabilidad administrado.|  
|ManagedInteropMethodSignature|win:UnicodeString|Firma del método de interoperabilidad administrado.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vea también

- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)

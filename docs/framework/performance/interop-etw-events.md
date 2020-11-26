---
title: Eventos ETW de interoperabilidad
description: Revise los eventos ETW de interoperabilidad (seguimiento de eventos para Windows), que capturan información sobre la generación de código auxiliar del lenguaje intermedio de Microsoft (MSIL) & almacenamiento en caché en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
ms.openlocfilehash: 8e92a1492d0295fb71473843752cb4c6184d3604
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242193"
---
# <a name="interop-etw-events"></a>Eventos ETW de interoperabilidad

Los eventos de interoperabilidad capturan información sobre el almacenamiento en caché y la generación de código auxiliar del lenguaje intermedio (MSIL) de Microsoft.  

## <a name="ilstubgenerated-event"></a>Evento ILStubGenerated

En la tabla siguiente se muestra la palabra clave y el nivel. (Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0 x 2000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|88|Se generó código auxiliar MSIL.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
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
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|89|Se tuvo acceso a la memoria caché MSIL.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
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

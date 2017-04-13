---
title: "Interop ETW Events | Microsoft Docs"
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
  - "interop events [.NET Framework]"
  - "ETW, interop events (CLR)"
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Interop ETW Events
<a name="top"></a> Los eventos de interoperabilidad capturan información sobre el almacenamiento en caché y la generación de código auxiliar del lenguaje intermedio \(MSIL\) de Microsoft.  
  
 Esta categoría consta de los siguientes eventos:  
  
-   [Evento ILStubGenerated](#ilstubgenerated_event)  
  
-   [Evento ILStubCacheHit](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## Evento ILStubGenerated  
 En la tabla siguiente se muestra la palabra clave y el nivel. \(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)\).  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`InteropKeyword` \(0 x 2000\)|Informativo \(4\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`ILStubGenerated`|88|Se generó código auxiliar MSIL.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|ModuleID|win:UInt16|Identificador del módulo.|  
|StubMethodID|win:UInt64|Identificador del método de código auxiliar.|  
|StubFlags|win:UInt64|Marcas para el código auxiliar:<br /><br /> 0x1 \- Interoperabilidad inversa.<br /><br /> 0x2 \- Interoperabilidad COM.<br /><br /> 0x4 \- Código auxiliar generado por NGen.exe.<br /><br /> 0x8 \- Delegado.<br /><br /> 0x10 \- Argumento variable.<br /><br /> 0x20 \- Destinatario no administrado.|  
|ManagedInteropMethodToken|win:UInt32|Token del método de interoperabilidad administrado.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Espacio de nombres del método de interoperabilidad administrado.|  
|ManagedInteropMethodName|win:UnicodeString|Nombre del método de interoperabilidad administrado.|  
|ManagedInteropMethodSignature|win:UnicodeString|Firma del método de interoperabilidad administrado.|  
|NativeMethodSignature|win:UnicodeString|Firma del método nativo.|  
|StubMethodSignature|win:UnicodeString|Firma del método de código auxiliar.|  
|StubMethodILCode|win:UnicodeString|Código MSIL para el método de código auxiliar.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="ilstubcachehit_event"></a>   
## Evento ILStubCacheHit  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`InteropKeyword` \(0 x 2000\)|Informativo \(4\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`ILStubCacheHit`|89|Se tuvo acceso a la memoria caché MSIL.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|ModuleID|win:UInt16|Identificador del módulo.|  
|StubMethodID|win:UInt64|Identificador del método de código auxiliar.|  
|ManagedInteropMethodToken|win:UInt32|Token del método de interoperabilidad administrado.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Espacio de nombres del método de interoperabilidad administrado.|  
|ManagedInteropMethodName|win:UnicodeString|Nombre del método de interoperabilidad administrado.|  
|ManagedInteropMethodSignature|win:UnicodeString|Firma del método de interoperabilidad administrado.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
## Vea también  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)
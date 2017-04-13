---
title: "JIT Tracing ETW Events | Microsoft Docs"
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
  - "JIT tracing events [.NET Framework]"
  - "ETW, JIT tracing events (CLR)"
ms.assetid: 926adde2-c123-452e-bf4f-4b977bf06ffb
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# JIT Tracing ETW Events
<a name="top"></a> Estos eventos recopilan información relativa a si la inclusión Just\-In\-Time \(JIT\) y las llamadas de cola JIT se realizan correctamente o no.  
  
 Los eventos de seguimiento JIT constan de las dos categorías siguientes:  
  
-   [Eventos de inclusión JIT](#jit_inlining_events)  
  
-   [Eventos de llamada de cola JIT](#jit_tail_call_events)  
  
<a name="jit_inlining_events"></a>   
## Eventos de inclusión JIT  
  
### Evento MethodJitInliningFailed  
 En la tabla siguiente se muestra la palabra clave y el nivel. \(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)\).  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`JITTracingKeyword` \(0 x 10\)|Detallado \(5\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`MethodJitInliningFailed`|186|Error de inclusión de JIT.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Espacio de nombres del método que se está compilando.|  
|MethodBeingCompiledName|win:UnicodeString|Nombre del método que se está compilando.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Firma del método que se está compilando.|  
|InlinerNamespace|win:UnicodeString|Espacio de nombres del método para el que el compilador JIT intenta generar código.|  
|InlinerName|win:UnicodeString|Nombre del método para el que el compilador intenta generar código. Esto puede no ser igual que `MethodBeingCompiledName` si el compilador está intentando incluir código en `MethodBeingCompiledName`, en lugar de generar una llamada a `InlinerName`.|  
|InlinerNameSignature|win:UnicodeString|Firma para el inclusor.|  
|InlineeNamespace|win:UnicodeString|Espacio de nombres del incluido.|  
|InlineeName|win:UnicodeString|Método que el compilador está intentando incluir \(genera una llamada\).|  
|InlineeNameSignature|win:UnicodeString|Firma para el incluido.|  
|FailAlways|win:Boolean|Sugerencia para el compilador JIT en la que la inclusión siempre producirá un error para el incluido.|  
|FailReason|win:UnicodeString|INLINE\_NEVER quiere decir que un intento de inclusión anterior determinó que la inclusión no se realizaría nunca correctamente por alguna otra razón. De lo contrario, texto de forma libre.|  
|ClrInstanceID|win:UnicodeString|Identificador único para la instancia de CLR o CoreCLR.|  
  
### Evento MethodJitInliningSucceeded  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`JITTracingKeyword` \(0 x 10\)|Detallado \(5\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`MethodJitInliningSucceeded`|185|El método de inclusión se realizó correctamente.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Espacio de nombres del método que se está compilando.|  
|MethodBeingCompiledName|win:UnicodeString|Nombre del método que se está compilando.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Firma del método que se está compilando.|  
|InlinerNamespace|win:UnicodeString|Espacio de nombres del método para el que el compilador JIT intenta generar código.|  
|InlinerName|win:UnicodeString|Nombre del método para el que el compilador intenta generar código. Esto puede no ser igual que `MethodBeingCompiledName` si el compilador está intentando incluir código en `MethodBeingCompiledName`, en lugar de generar una llamada a `InlinerName`.|  
|InlinerNameSignature|win:UnicodeString|Firma para el inclusor.|  
|InlineeNamespace|win:UnicodeString|Espacio de nombres del incluido.|  
|InlineeName|win:UnicodeString|Método que el compilador está intentando incluir \(genera una llamada\).|  
|InlineeNameSignature|win:UnicodeString|Firma para el incluido.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="jit_tail_call_events"></a>   
## Eventos de llamada de cola JIT  
  
### Evento MethodJITTailCallFailed  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`JITTracingKeyword` \(0 x 10\)|Detallado \(5\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`MethodJitTailCallFailed`|189|Error en la llamada de cola del método.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Espacio de nombres del método que se está compilando.|  
|MethodBeingCompiledName|win:UnicodeString|Nombre del método que se está compilando.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Firma del método que se está compilando.|  
|CallerNamespace|win:UnicodeString|Espacio de nombres del método para el que el compilador JIT intenta generar código.|  
|CallerName|win:UnicodeString|Nombre del método para el que el compilador intenta generar código.|  
|CallerNameSignature|win:UnicodeString|Firma del llamador.|  
|CalleeNamespace|win:UnicodeString|Espacio de nombres del destinatario.|  
|CalleeName|win:UnicodeString|Método al que compilador está intentando realizar una llamada de cola \(no genera una llamada\).|  
|CalleeNameSignature|win:UnicodeString|Firma para el destinatario.|  
|TailPrefix|win:Boolean|Prefijo para la llamada de cola.|  
|FailReason|win:UnicodeString|Razón por la que se produjo un error en la llamada de cola.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
### Evento MethodJITTailCallSucceeded  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`JITTracingKeyword` \(0 x 10\)|Detallado \(5\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`MethodJitTailCallSucceeded`|188|La llamada de cola del método se realizó correctamente.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Espacio de nombres del método que se está compilando.|  
|MethodBeingCompiledName|win:UnicodeString|Nombre del método que se está compilando.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Firma del método que se está compilando.|  
|CallerNamespace|win:UnicodeString|Espacio de nombres del método para el que el compilador JIT intenta generar código.|  
|CallerName|win:UnicodeString|Nombre del método para el que el compilador intenta generar código.|  
|CallerNameSignature|win:UnicodeString|Firma del llamador.|  
|CalleeNamespace|win:UnicodeString|Espacio de nombres del destinatario.|  
|CalleeName|win:UnicodeString|Método al que compilador está intentando realizar una llamada de cola \(no genera una llamada\).|  
|CalleeNameSignature|win:UnicodeString|Firma para el destinatario.|  
|TailPrefix|win:Boolean|Prefijo para la llamada de cola.|  
|TailCallType|win:UnicodeString|Tipo de llamada de cola.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## Vea también  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)
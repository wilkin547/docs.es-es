---
title: "Eventos ETW de método"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 353ae034381ab29787aba1c1c362f4c6fc57da7e
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="method-etw-events"></a>Eventos ETW de método
<a name="top"></a> Estos eventos recopilan información que es específica de los métodos. La carga de estos eventos es necesaria para la resolución de símbolos. Además, estos eventos proporcionan información útil como el número de veces que se llama a un método.  
  
 Todos los eventos de método tienen un nivel de “Informativo (4)”. Todos los eventos detallados de método tienen un nivel de “Detallado (5)”.  
  
 Todos los eventos de método se generan mediante la palabra clave `JITKeyword` (0x10) o la palabra clave `NGenKeyword` (0x20) con el proveedor de runtime, o `JitRundownKeyword` (0x10) o `NGENRundownKeyword` (0x20) con el proveedor de detención.  
  
 Los eventos de método CLR se dividen a su vez en los siguientes tipos:  
  
-   [Eventos de método CLR](#clr_method_events)  
  
-   [Eventos de marcador de método CLR](#clr_method_marker_events)  
  
-   [Eventos detallados de método CLR](#clr_method_verbose_events)  
  
-   [Evento MethodJittingStarted](#methodjittingstarted_event)  
  
<a name="clr_method_events"></a>   
## <a name="clr-method-events"></a>Eventos de método CLR  
 En la tabla siguiente se muestra la palabra clave y el nivel. (Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`JITKeyword` (0x10)|Informativo (4)|  
|`NGenKeyword` (0x20)|Informativo (4)|  
|`JitRundownKeyword` (0x10)|Informativo (4)|  
|`NGENRundownKeyword` (0x20)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`MethodLoad_V1`|136|Se genera cuando un método se carga just-in-time (carga JIT) o se carga una imagen NGEN. Los métodos dinámicos y genéricos no usan esta versión para cargas de método. Las aplicaciones auxiliares de JIT nunca usan esta versión.|  
|`MethodUnLoad_V1`|137|Se genera cuando se descarga un módulo o se destruye un dominio de aplicación. Los métodos dinámicos nunca usan esta versión para descargas de método.|  
|`MethodDCStart_V1`|137|Enumera los métodos durante una detención de inicio.|  
|`MethodDCEnd_V1`|138|Enumera los métodos durante una detención de fin.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|MethodID|win:UInt64|Identificador único de un método. Para los métodos auxiliares JIT, se establece en la dirección de inicio del método.|  
|ModuleID|win:UInt64|Identificador del módulo al que pertenece este método (0 para aplicaciones auxiliares de JIT).|  
|MethodStartAddress|win:UInt64|Dirección de inicio del método.|  
|MethodSize|win:UInt32|Tamaño del método.|  
|MethodToken|win:UInt32|0 para métodos dinámicos y aplicaciones auxiliares de JIT.|  
|MethodFlags|win:UInt32|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0x4: método de código compilado JIT (en caso contrario, código de imagen nativa de NGEN).<br /><br /> 0x8: método auxiliar.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="clr_method_marker_events"></a>   
## <a name="clr-method-marker-events"></a>Eventos de marcador de método CLR  
 Además, estos eventos solo se generan con el proveedor de detención y significan el final de la enumeración de método durante una detención de inicio o fin. (Es decir, se generan cuando la palabra clave `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`o `AppDomainResourceManagementRundownKeyword` está habilitada.)  
  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementRundownKeyword` (0x800)|Informativo (4)|  
|`JitRundownKeyword` (0x10)|Informativo (4)|  
|`NGENRundownKeyword` (0x20)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|----------------|  
|`DCStartInit_V1`|147|Se envía antes del inicio de la enumeración durante un informe detallado de inicio.|  
|`DCStartComplete_V1`|145|Se envía al final de la enumeración durante un informe detallado de inicio.|  
|`DCEndInit_V1`|148|Se envía antes del inicio de la enumeración durante un informe detallado de fin.|  
|`DCEndComplete_V1`|146|Se envía al final de la enumeración durante un informe detallado de fin.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="clr_method_verbose_events"></a>   
## <a name="clr-method-verbose-events"></a>Eventos detallados de método CLR  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`JITKeyword` (0x10)|Detallado (5)|  
|`NGenKeyword` (0x20)|Detallado (5)|  
|`JitRundownKeyword` (0x10)|Detallado (5)|  
|`NGENRundownKeyword` (0x20)|Detallado (5)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`MethodLoadVerbose_V1`|143|Se genera cuando la carga de un método es JIT o se carga una imagen NGEN. Los métodos dinámicos y genéricos siempre usan esta versión para cargas de método. Las aplicaciones auxiliares de JIT siempre usan esta versión.|  
|`MethodUnLoadVerbose_V1`|144|Se genera cuando se destruye un método dinámico, se descarga un módulo o se destruye un dominio de aplicación. Los métodos dinámicos siempre usan esta versión para descargas de método.|  
|`MethodDCStartVerbose_V1`|141|Enumera los métodos durante una detención de inicio.|  
|`MethodDCEndVerbose_V1`|142|Enumera los métodos durante una detención de fin.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|MethodID|win:UInt64|Identificador único del método. Para los métodos auxiliares JIT, se establece en la dirección de inicio del método.|  
|ModuleID|win:UInt64|Identificador del módulo al que pertenece este método (0 para aplicaciones auxiliares de JIT).|  
|MethodStartAddress|win:UInt64|Dirección de inicio.|  
|MethodSize|win:UInt32|Longitud de método.|  
|MethodToken|win:UInt32|0 para métodos dinámicos y aplicaciones auxiliares de JIT.|  
|MethodFlags|win:UInt32|0x1: método dinámico.<br /><br /> 0x2: método genérico.<br /><br /> 0 x 4: método compilado JIT (de lo contrario, generado por NGen.exe)<br /><br /> 0x8: método auxiliar.|  
|MethodNameSpace|win:UnicodeString|Nombre del espacio de nombres completo que está asociado al método.|  
|MethodName|win:UnicodeString|Nombre de clase completo que está asociado al método.|  
|MethodSignature|win:UnicodeString|Signatura del método (lista separada por comas de nombres de tipo).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="methodjittingstarted_event"></a>   
## <a name="methodjittingstarted-event"></a>Evento MethodJittingStarted  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`JITKeyword` (0x10)|Detallado (5)|  
|`NGenKeyword` (0x20)|Detallado (5)|  
|`JitRundownKeyword` (0x10)|Detallado (5)|  
|`NGENRundownKeyword` (0x20)|Detallado (5)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`MethodJittingStarted`|145|Se genera cuando se está realizando la compilación JIT de un método.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|MethodID|win:UInt64|Identificador único del método.|  
|ModuleID|win:UInt64|Identificador del módulo al que pertenece este método.|  
|MethodToken|win:UInt32|0 para métodos dinámicos y aplicaciones auxiliares de JIT.|  
|MethodILSize|win:UInt32|El tamaño del lenguaje intermedio de Microsoft (MSIL) del método en el que se está realizando la compilación JIT.|  
|MethodNameSpace|win:UnicodeString|Nombre de clase completo que está asociado al método.|  
|MethodName|win:UnicodeString|Nombre del método.|  
|MethodSignature|win:UnicodeString|Signatura del método (lista separada por comas de nombres de tipo).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vea también  
 [CLR ETW Events (Eventos ETW de CLR)](../../../docs/framework/performance/clr-etw-events.md)


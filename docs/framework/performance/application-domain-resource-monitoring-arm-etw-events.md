---
title: "Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)"
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
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a93e8cc1ab0b7488f920b556d2073d2813c3b7a9
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a>Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)
<a name="top"></a> Estos eventos proporcionan información de diagnóstico detallada sobre el estado de un dominio de aplicación. Puede utilizar estos eventos o la característica de supervisión de recursos del dominio de aplicación (ARM) para obtener la misma información.  
  
 Esta categoría consta de los siguientes eventos:  
  
-   [Evento ThreadCreated](#threadcreated_event)  
  
-   [Evento AppDomainMemAllocated](#appdomainmemallocated_event)  
  
-   [Evento AppDomainMemSurvived](#appdomainmemsurvived_event)  
  
-   [Evento ThreadAppDomainEnter](#threadappdomainenter_event)  
  
-   [Evento ThreadTerminated](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a>Evento ThreadCreated  
 Este evento también se genera con el proveedor de informe detallado como `ThreadDC` (con la palabra clave `AppDomainResourceManagementRundownKeyword` ). Es el único evento que se provoca con el proveedor de informe detallado en esta categoría.  
  
 En la tabla siguiente se muestra la palabra clave y el nivel. (Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|85|Se crea un subproceso para el dominio de aplicación.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ThreadID|win:UInt64|Se creó el identificador del subproceso.|  
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación para el que se notifica la actividad de subproceso.|  
|Marcas|win:UInt32|Marcas de creación de subproceso.|  
|ManagedThreadIndex|win:UInt32|Se creó el índice administrado del subproceso.|  
|OSThreadID|win:UInt32|Se creó el identificador del sistema operativo del subproceso.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a>Evento AppDomainMemAllocated  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|83|Cada vez que se asignan 4 MB de memoria (aproximadamente) en el dominio de aplicación.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación para el que se notifica el uso de recursos.|  
|Allocated|win:UInt64|Número total de bytes asignado en este dominio de aplicación desde que se creó el dominio de aplicación (sin restar la cantidad de memoria liberada).|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a>Evento AppDomainMemSurvived  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|84|Fnalizadas todas las recolecciones de elementos no utilizados.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|AppDomainID|win:UInt64|Identificador del dominio para el que recurso que se notifica el uso de recursos.|  
|Survived|win:UInt64|Número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que se sabe que están contenidos en este dominio de aplicación. Este número es preciso y completo después de una recolección completa, pero puede estar incompleto después de una recolección efímera.|  
|ProcessSurvived|win:UInt64|Bytes totales que sobrevivieron de la última recolección. Después de una recolección completa, este número representa el número de bytes que se mantienen activos en montones administrados. Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a>Evento ThreadAppDomainEnter  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|87|Un subproceso entra en un dominio de aplicación.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ThreadID|win:UInt64|Identifiador del subproceso.|  
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a>Evento ThreadTerminated  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|  
|`ThreadingKeyword` (0x10000)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|86|Finaliza un subproceso.|  
  
 En la siguiente tabla, se muestran los datos del evento:  
  
|Nombre de campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|ThreadID|win:UInt64|Identifiador del subproceso.|  
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Vea también  
 [CLR ETW Events (Eventos ETW de CLR)](../../../docs/framework/performance/clr-etw-events.md)


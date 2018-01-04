---
title: AppDomainInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed5053dd69628a9f5ff7318ce7fe772f42de6e24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="appdomaininfo"></a>AppDomainInfo
Información del dominio de aplicaciones  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase AppDomainInfo no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase AppDomainInfo tiene las propiedades siguientes:  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. de appdomain.  
  
### <a name="isdefault"></a>IsDefault  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si appdomain es el appdomain predeterminado.  
  
### <a name="logmalformedmessages"></a>LogMalformedMessages  
 Tipo de datos: booleano  
  
 Tipo de acceso: lectura/escritura  
  
 Valor booleano que especifica si se registran los mensajes con formato erróneo.  
  
### <a name="logmessagesatservicelevel"></a>LogMessagesAtServiceLevel  
 Tipo de datos: booleano  
  
 Tipo de acceso: lectura/escritura  
  
 Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).  
  
### <a name="logmessagesattransportlevel"></a>LogMessagesAtTransportLevel  
 Tipo de datos: booleano  
  
 Tipo de acceso: lectura/escritura  
  
 Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.  
  
### <a name="messageloggingtracelisteners"></a>MessageLoggingTraceListeners  
 Matriz TraceListener de tipo de datos  
  
 Tipo de acceso: solo lectura  
  
 Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.  
  
### <a name="name"></a>nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre de appdomain.  
  
### <a name="performancecounters"></a>PerformanceCounters  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El ámbito de contadores de rendimiento activos en el appdomain.  
  
### <a name="processid"></a>ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. de proceso.  
  
### <a name="serviceconfigpath"></a>ServiceConfigPath  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Ruta de acceso a la configuración del servicio.  
  
### <a name="tracelevel"></a>TraceLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: lectura/escritura  
  
 El nivel de seguimiento del origen de seguimiento de System.Wmi.  
  
### <a name="servicemodeltracelisteners"></a>ServiceModelTraceListeners  
 Matriz TraceListener de tipo de datos  
  
 Tipo de acceso: solo lectura  
  
 Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|

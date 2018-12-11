---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127087"
---
# <a name="appdomaininfo"></a>AppDomainInfo
Información del dominio de aplicaciones  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
  
 Tipo de acceso: De sólo lectura  
  
 El id. de appdomain.  
  
### <a name="isdefault"></a>IsDefault  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Indica si appdomain es el appdomain predeterminado.  
  
### <a name="logmalformedmessages"></a>LogMalformedMessages  
 Tipo de datos: booleano  
  
 Tipo de acceso: Lectura/escritura  
  
 Valor booleano que especifica si se registran los mensajes con formato erróneo.  
  
### <a name="logmessagesatservicelevel"></a>LogMessagesAtServiceLevel  
 Tipo de datos: booleano  
  
 Tipo de acceso: Lectura/escritura  
  
 Valor booleano que especifica si los mensajes se siguen en el nivel de servicio (antes del cifrado y las transformaciones relacionadas con transporte).  
  
### <a name="logmessagesattransportlevel"></a>LogMessagesAtTransportLevel  
 Tipo de datos: booleano  
  
 Tipo de acceso: Lectura/escritura  
  
 Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.  
  
### <a name="messageloggingtracelisteners"></a>MessageLoggingTraceListeners  
 Tipo de datos: Matriz TraceListener  
  
 Tipo de acceso: De sólo lectura  
  
 Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.  
  
### <a name="name"></a>nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El nombre de appdomain.  
  
### <a name="performancecounters"></a>PerformanceCounters  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El ámbito de contadores de rendimiento activos en el appdomain.  
  
### <a name="processid"></a>ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El id. de proceso.  
  
### <a name="serviceconfigpath"></a>ServiceConfigPath  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Ruta de acceso a la configuración del servicio.  
  
### <a name="tracelevel"></a>TraceLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: Lectura/escritura  
  
 El nivel de seguimiento del origen de seguimiento de System.Wmi.  
  
### <a name="servicemodeltracelisteners"></a>ServiceModelTraceListeners  
 Tipo de datos: Matriz TraceListener  
  
 Tipo de acceso: De sólo lectura  
  
 Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|

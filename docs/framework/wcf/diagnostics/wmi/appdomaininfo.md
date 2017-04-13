---
title: "AppDomainInfo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# AppDomainInfo
Información del dominio de aplicaciones  
  
## Sintaxis  
  
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
  
## Métodos  
 La clase AppDomainInfo no define ningún método.  
  
## Propiedades  
 La clase AppDomainInfo tiene las propiedades siguientes:  
  
### AppDomainId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. de appdomain.  
  
### IsDefault  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si appdomain es el appdomain predeterminado.  
  
### LogMalformedMessages  
 Tipo de datos: booleano  
  
 Tipo de acceso: lectura\/escritura  
  
 Valor booleano que especifica si se registran los mensajes con formato erróneo.  
  
### LogMessagesAtServiceLevel  
 Tipo de datos: booleano  
  
 Tipo de acceso: lectura\/escritura  
  
 Valor booleano que especifica si los mensajes se siguen en el nivel de servicio \(antes del cifrado y las transformaciones relacionadas con transporte\).  
  
### LogMessagesAtTransportLevel  
 Tipo de datos: booleano  
  
 Tipo de acceso: lectura\/escritura  
  
 Valor booleano que especifica si los mensajes se siguen en el nivel de transporte.  
  
### MessageLoggingTraceListeners  
 Matriz TraceListener de tipo de datos  
  
 Tipo de acceso: solo lectura  
  
 Los agentes de escucha de seguimiento de colección que escuchan el origen de seguimiento de System.Wmi.MessageLogging.  
  
### Nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre de appdomain.  
  
### PerformanceCounters  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El ámbito de contadores de rendimiento activos en el appdomain.  
  
### ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. de proceso.  
  
### ServiceConfigPath  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Ruta de acceso a la configuración del servicio.  
  
### TraceLevel  
 Tipo de datos: cadena  
  
 Tipo de acceso: lectura\/escritura  
  
 El nivel de seguimiento del origen de seguimiento de System.Wmi.  
  
### ServiceModelTraceListeners  
 Matriz TraceListener de tipo de datos  
  
 Tipo de acceso: solo lectura  
  
 Una colección de agentes de escucha del origen de seguimiento de System.ServiceModel.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|
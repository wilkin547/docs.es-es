---
title: "ConnectionOrientedTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## Sintaxis  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## Métodos  
 La clase ConnectionOrientedTransportBindingElement no define ningún método.  
  
## Propiedades  
 La clase ConnectionOrientedTransportBindingElement tiene las propiedades siguientes:  
  
### ChannelInitializationTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El timespan que especifica cuánto tiempo tiene la inicialización del canal para completarse antes de que se agote el tiempo de espera.  
  
### ConnectionBufferSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El tamaño del búfer usado para transmitir un fragmento del mensaje serializado en la conexión del cliente o servicio.  
  
### HostNameComparisonMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.  
  
### MaxBufferSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo del búfer que se va a usar.  
  
### MaxOutputDelay  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo máximo de tiempo que un fragmento de un mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.  
  
### MaxPendingAccepts  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de subprocesos de aceptación asincrónica pendientes disponibles para procesar conexiones entrantes en el servicio.  
  
### MaxPendingConnections  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de conexiones pendientes.  
  
### TransferMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor que especifica si los mensajes están almacenados en búfer o se transmiten mediante el transporte orientado a la conexión.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
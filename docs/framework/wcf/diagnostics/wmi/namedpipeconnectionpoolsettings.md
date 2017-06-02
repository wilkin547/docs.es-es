---
title: "NamedPipeConnectionPoolSettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# NamedPipeConnectionPoolSettings
NamedPipeConnectionPoolSettings  
  
## Sintaxis  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## Métodos  
 La clase NamedPipeConnectionPoolSettings no define ningún método.  
  
## Propiedades  
 La clase NamedPipeConnectionPoolSettings tiene las siguientes propiedades:  
  
### GroupName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre del grupo de conexiones utilizado por el elemento de enlace.  
  
### IdleTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.  
  
### MaxOutboundConnectionsPerEndpoint  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de conexiones salientes para cada extremo en el cliente.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
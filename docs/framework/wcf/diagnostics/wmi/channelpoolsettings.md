---
title: "ChannelPoolSettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ChannelPoolSettings
ChannelPoolSettings  
  
## Sintaxis  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## Métodos  
 La clase ChannelPoolSettings no define ningún método.  
  
## Propiedades  
 La clase ChannelPoolSettings tiene las propiedades siguientes:  
  
### IdleTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.  
  
### LeaseTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.  
  
### MaxOutboundChannelsPerEndpoint  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de canales de salida para cada extremo.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
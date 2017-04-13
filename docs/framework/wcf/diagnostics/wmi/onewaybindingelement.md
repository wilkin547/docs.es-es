---
title: "OneWayBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OneWayBindingElement
OneWayBindingElement  
  
## Sintaxis  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## Métodos  
 La clase OneWayBindingElement no define ningún método.  
  
## Propiedades  
 La clase OneWayBindingElement tiene las propiedades siguientes:  
  
### ChannelPoolSettings  
 Tipo de datos: ChannelPoolSettings  
  
 Tipo de acceso: solo lectura  
  
 La configuración del grupo de canales.  
  
### MaxAcceptedChannels  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de canales aceptados.  
  
### PacketRoutable  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Valor que indica si el paquete se puede enrutar.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
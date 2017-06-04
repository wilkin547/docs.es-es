---
title: "Clase de canal | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Clase de canal
Canal  
  
## Sintaxis  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## Métodos  
 La clase Canal no define ningún método.  
  
## Propiedades  
 La clase Canal tiene las propiedades siguientes.  
  
### LocalAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Extremo local para el canal.  
  
### ref  
 Tipo de datos: extremo  
  
 Tipo de acceso: solo lectura  
  
 Una referencia al extremo al que se conecta el canal.  
  
### RemoteAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Dirección remota asociada al canal.  
  
### SessionId  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Identificador de la sesión actual, si lo hubiera.  
  
### Tipo  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El tipo de canal.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.ChannelBase>
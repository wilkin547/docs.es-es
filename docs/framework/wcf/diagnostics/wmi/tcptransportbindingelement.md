---
title: "TcpTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# TcpTransportBindingElement
TcpTransportBindingElement  
  
## Sintaxis  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## Métodos  
 La clase TcpTransportBindingElement no define ningún método.  
  
## Propiedades  
 La clase TcpTransportBindingElement tiene las propiedades siguientes:  
  
### connectionPoolSettings  
 Tipo de datos: TcpConnectionPoolSettings  
  
 Tipo de acceso: solo lectura  
  
 Agrupación de conexiones.  
  
### ListenBacklog  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de solicitudes de conexión en cola que pueden estar pendientes.  
  
### PortSharingEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Valor booleano que especifica si el uso compartido de los puertos TCP está habilitado para esta conexión.  
  
### TeredoEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si Teredo \(una tecnología para direccionar clientes que están detrás de firewalls\) está habilitada.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
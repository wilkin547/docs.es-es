---
title: "PeerSecuritySettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# PeerSecuritySettings
PeerSecuritySettings  
  
## Sintaxis  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## Métodos  
 La clase PeerSecuritySettings no define ningún método.  
  
## Propiedades  
 La clase PeerSecuritySettings tiene las siguientes propiedades:  
  
### Modo  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Si un extremo configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.  
  
### Transporte  
 Tipo de datos: PeerTransportSecuritySettings  
  
 Tipo de acceso: solo lectura  
  
 Valores de seguridad de transporte.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.PeerSecuritySettings>
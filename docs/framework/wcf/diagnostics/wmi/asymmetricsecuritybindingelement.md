---
title: "AsymmetricSecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# AsymmetricSecurityBindingElement
AsymmetricSecurityBindingElement  
  
## Sintaxis  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## Métodos  
 La clase AsymmetricSecurityBindingElement no define ningún método.  
  
## Propiedades  
 La clase AsymmetricSecurityBindingElement tiene las propiedades siguientes:  
  
### MessageProtectionOrder  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El orden de cifrado de mensajes y firma para este enlace.  
  
### RequireSignatureConfirmation  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Si el enlace requiere la confirmación de la firma.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
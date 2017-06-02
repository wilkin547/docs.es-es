---
title: "SymmetricSecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# SymmetricSecurityBindingElement
SymmetricSecurityBindingElement  
  
## Sintaxis  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## Métodos  
 La clase SymmetricSecurityBindingElement no define ningún método.  
  
## Propiedades  
 La clase SymmetricSecurityBindingElement tiene las propiedades siguientes:  
  
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
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
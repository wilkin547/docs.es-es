---
title: "PrivacyNoticeBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## Sintaxis  
  
```  
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## Métodos  
 La clase PrivacyNoticeBindingElement no define ningún método.  
  
## Propiedades  
 La clase PrivacyNoticeBindingElement tiene las propiedades siguientes:  
  
### PrivacyNoticeVersion  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 La versión del aviso de privacidad.  
  
### Url  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La dirección URL en la que se encuentra el aviso de privacidad.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
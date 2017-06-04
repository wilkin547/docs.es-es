---
title: "CustomBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# CustomBindingElement
CustomBindingElement  
  
## Sintaxis  
  
```  
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## Métodos  
 La clase CustomBindingElement no define ningún método.  
  
## Propiedades  
 La clase CustomBindingElement tiene la propiedad siguiente:  
  
### Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Cadena que contiene el nombre de configuración del enlace.  Este valor es una cadena definida por el usuario que actúa como cadena de identificación para el enlace personalizado.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.CustomBinding>
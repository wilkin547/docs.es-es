---
title: "ServiceToEndpointAssociation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceToEndpointAssociation
Asigna un servicio a un extremo.  
  
## Sintaxis  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## Métodos  
 La clase ServiceToEndpointAssociation no define ningún método.  
  
## Propiedades  
 La clase ServiceToEndpointAssociation tiene las propiedades siguientes:  
  
### ref  
 Tipo de datos: servicio  
  
 Tipo de acceso: solo lectura  
Calificadores: Clave  
  
 El servicio asociado con el extremo.  
  
### ref  
 Tipo de datos: extremo  
  
 Tipo de acceso: solo lectura  
Calificadores: Clave  
  
 El extremo asociado con el servicio.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|
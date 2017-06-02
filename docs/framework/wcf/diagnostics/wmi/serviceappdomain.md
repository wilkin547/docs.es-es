---
title: "ServiceAppDomain | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceAppDomain
Asigna un servicio a un dominio de aplicación.  
  
## Sintaxis  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## Métodos  
 La clase ServiceAppDomain no define ningún método.  
  
## Propiedades  
 La clase ServiceAppDomain posee las siguientes propiedades:  
  
### ref  
 Tipo de datos: servicio               
 Calificadores: clave  
  
 Tipo de acceso: solo lectura  
  
 Servicio de este dominio de aplicación.  
  
### ref  
 Tipo de datos: AppDomainInfo               
 Calificadores: clave  
  
 Tipo de acceso: solo lectura  
  
 Contiene propiedades del dominio de aplicación.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|
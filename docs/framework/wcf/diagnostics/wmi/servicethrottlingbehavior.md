---
title: "ServiceThrottlingBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## Sintaxis  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## Métodos  
 La clase ServiceThrottlingBehavior no define ningún método.  
  
## Propiedades  
 La clase ServiceThrottlingBehavior tiene las propiedades siguientes:  
  
### MaxConcurrentCalls  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de mensajes que se procesan activamente en todos los objetos de distribuidor en un ServiceHost.  
  
### MaxConcurrentInstances  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de objetos de servicio que se pueden ejecutar simultáneamente.  
  
### MaxConcurrentSessions  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de sesiones que un host puede aceptar al mismo tiempo.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
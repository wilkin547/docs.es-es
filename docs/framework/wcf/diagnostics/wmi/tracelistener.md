---
title: "TraceListener | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2c0b595-a384-4eb3-b94d-1b3be7cc7a5c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# TraceListener
TraceListener  
  
## Sintaxis  
  
```  
class TraceListener  
{  
  string Name;  
  TraceListenerArgument TraceListenerArguments[];  
};  
```  
  
## Métodos  
 La clase TraceListener no define ningún método.  
  
## Propiedades  
 La clase TraceListener tiene las propiedades siguientes:  
  
### Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre del agente de escucha de seguimiento.  
  
### TraceListenerArgument  
 Tipo de datos: Matriz de TraceListenerArgument  
  
 Tipo de acceso: solo lectura  
  
 Los argumentos del agente de escucha de seguimiento.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|
---
title: "ActivityTransfer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# ActivityTransfer
Evento de transferencia de actividad  
  
## Sintaxis  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## Métodos  
 La clase ActivityTransfer no define ningún método.  
  
## Propiedades  
 La clase ActivityTransfer posee las propiedades siguientes:  
  
### ActivityID  
  
-   Tipo de datos: objeto                   
     Tipo de acceso: solo lectura  
  
-   Id. de actividad  
  
### RelatedActivityID  
  
-   Tipo de datos: objeto                   
     Tipo de acceso: solo lectura  
  
-   Id. de actividad relacionada  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel.|
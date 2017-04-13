---
title: "WSAT_TraceRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# WSAT_TraceRecord
WSAT\_TraceRecord  
  
## Sintaxis  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## Métodos  
 La clase WSAT\_TraceRecord no define ningún método.  
  
## Propiedades  
 La clase WSAT\_TraceRecord tiene las propiedades siguientes:  
  
### ActivityID  
 Tipo de datos: objeto  
Tipo de acceso: solo lectura  
  
 El id. de actividad del registro de seguimiento.  
  
### EventID  
 Tipo de datos: sint32  
Tipo de acceso: solo lectura  
  
 El id. de evento del registro de seguimiento.  
  
### TraceRecord  
 Tipo de datos: cadena  
Tipo de acceso: solo lectura  
  
 Registro de seguimiento  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|
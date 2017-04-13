---
title: "OperationBehaviorAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## Sintaxis  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## Métodos  
 La clase OperationBehaviorAttribute no define ningún método.  
  
## Propiedades  
 La clase OperationBehaviorAttribute tiene las propiedades siguientes:  
  
### AutoDisposeParameters  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 El estado de la característica de eliminación automática para parámetros.  
  
### Suplantación  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Indica el nivel de suplantación del llamador que la operación admite.  
  
### ReleaseInstanceMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Indica cuándo durante el curso de una invocación de la operación debe reciclarse el objeto.  
  
### TransactionAutoComplete  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si confirmar automáticamente la transacción actual si no se produce ninguna excepción no controlada.  
  
### TransactionScopeRequired  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si la operación requiere una transacción.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
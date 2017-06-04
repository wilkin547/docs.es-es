---
title: "Contract | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Contract
Contrato  
  
## Sintaxis  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## Métodos  
 La clase Contrato no define ningún método.  
  
## Propiedades  
 La clase Contrato tiene las siguientes propiedades:  
  
### AppDomainId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. del appdomain de appdomain que hospeda el contrato.  
  
### Comportamientos  
 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Los comportamientos asociados a este contrato.  
  
### Nombre  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre del contrato en WSDL.  
  
### Espacio de nombres  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El espacio de nombres del elemento `portType` en WSDL.  
  
### Operaciones  
 Tipo de datos: matriz de operación  
  
 Tipo de acceso: solo lectura  
  
 Las operaciones de este contrato.  
  
### ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El Identificador del proceso del proceso que hospeda el contrato.  
  
### ref  
 Tipo de datos: Contrato  
  
 Tipo de acceso: solo lectura  
  
 El tipo de devolución de llamada cuando el contrato es un contrato dúplex.  
  
### SessionMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Indica si el contrato requiere el enlace asociado a este contrato para utilizar las sesiones del canal.  
  
### Tipo  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Tipo del contrato.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Description.ContractDescription>
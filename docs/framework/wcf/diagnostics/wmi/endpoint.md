---
title: "Extremo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Extremo
Extremo  
  
## Sintaxis  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## Métodos  
 La clase Endpoint define el método siguiente.  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|Recupera el nombre de instancia del contador de rendimiento de la operación|  
  
## Propiedades  
 La clase Endpoint posee las siguientes propiedades:  
  
### Dirección  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un URI que contiene la dirección del extremo.  
  
### AddressHeaders  
 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 La colección de encabezados de dirección adjunta a este extremo.  
  
### AddressIdentity  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La identidad del extremo.  
  
### AppDomainId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. del appdomain que hospeda al extremo.  
  
### Controles de comportamiento  
 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Colección de comportamientos implementada por este extremo.  
  
### Enlaces  
 Tipo de datos: enlace  
  
 Tipo de acceso: solo lectura  
  
 El enlace utilizado por este extremo.  
  
### ContractName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Cadena que especifica qué contrato está exponiendo este extremo.  
  
### CounterInstanceName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de la instancia del contador de rendimiento del extremo.  
  
### ListenUri  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El URI en el que el extremo realiza escuchas.  
  
### Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre único de este extremo.  
  
### ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El Id. del proceso que hospeda al extremo.  
  
### ref  
 Tipo de datos: Contrato  
  
 Tipo de acceso: solo lectura  
  
 El contrato que este extremo está exponiendo.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|
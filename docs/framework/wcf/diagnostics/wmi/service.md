---
title: "Servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Servicio
Servicio  
  
## Sintaxis  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## Métodos  
 La clase Service no define ningún método.  
  
## Propiedades  
 La clase Service posee las siguientes propiedades:  
  
### BaseAddresses  
 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Las direcciones base utilizadas por el servicio.  
  
### Comportamientos  
 Tipo de datos: matriz de comportamientos  
  
 Tipo de acceso: solo lectura  
  
 Los comportamientos asociados a este servicio.  
  
### ConfigurationName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 ServiceElement\_BehaviorConfiguration  
  
### CounterInstanceName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de la instancia de los contadores de rendimiento del servicio.  
  
### DistinguishedName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre de servicio en la dirección.  
  
### Extensiones  
 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Los contextos de instancia para las extensiones de la instancia de servicio.  
  
### Metadatos  
 Tipo de datos: matriz de cadenas  
  
 Tipo de acceso: solo lectura  
  
 Los valores de metadatos de servicio.  
  
### Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre único de este servicio.  
  
### Espacio de nombres  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El espacio de nombres del servicio.  
  
### Abierto  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El momento en el que se abrió el servicio.  
  
### OutgoingChannels  
 Tipo de datos: matriz de canal  
  
 Tipo de acceso: solo lectura  
  
 Los canales que salen de la instancia del servicio.  
  
### ProcessId  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El id. de proceso que hospeda el servicio.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|
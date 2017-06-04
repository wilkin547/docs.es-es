---
title: "Enlace | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Enlace
Enlace wmi  
  
## Sintaxis  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## Métodos  
 La clase Binding no define ningún método.  
  
## Propiedades  
 La clase Binding tiene las propiedades siguientes.  
  
### BindingElements  
 Tipo de datos: matriz de BindingElement  
  
 Tipo de acceso: solo lectura  
  
 La colección de elementos de enlace implementada por el enlace.  
  
### CloseTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de cierre.  
  
### Name  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Nombre del enlace.  
  
### Espacio de nombres  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Espacio de nombres XML del enlace.  
  
### OpenTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de apertura.  
  
### ReceiveTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de recepción.  
  
### Scheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema de transporte de URI utilizado por los generadores de canales y de agentes de escucha creados por el enlace.  
  
### SendTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El intervalo de tiempo proporcionado para que se complete una operación de envío.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.Binding>
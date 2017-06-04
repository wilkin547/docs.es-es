---
title: "SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# SecurityBindingElement
SecurityBindingElement  
  
## Sintaxis  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## Métodos  
 La clase SecurityBindingElement no define ningún método.  
  
## Propiedades  
 La clase SecurityBindingElement posee las siguientes propiedades:  
  
### DefaultAlgorithmSuite  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica los algoritmos que se van a utilizar con la clase.  
  
### IncludeTimestamp  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Valor booleano que especifica si cada mensaje contiene una marca de tiempo.  
  
### KeyEntropyMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Origen de la entropía utilizada para crear claves.  
  
### LocalServiceSecuritySettings  
 Tipo de datos: LocalServiceSecuritySettings  
  
 Tipo de acceso: solo lectura  
  
 Las propiedades de seguridad específicas del enlace del servicio local.  
  
### MessageSecurityVersion  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Versión utilizada para la seguridad del mensaje.  
  
### SecurityHeaderLayout  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Orden de los elementos en el encabezado de seguridad de este enlace.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
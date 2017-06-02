---
title: "ServiceDebugBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceDebugBehavior
ServiceDebugBehavior  
  
## Sintaxis  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## Métodos  
 La clase ServiceDebugBehavior no define ningún método.  
  
## Propiedades  
 La clase ServiceDebugBehavior posee las siguientes propiedades:  
  
### HttpHelpPageEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.  
  
### HttpHelpPageUrl  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.  
  
### HttpsHelpPageEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.  
  
### HttpsHelpPageUrl  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.  
  
### IncludeExceptionDetailInFaults  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
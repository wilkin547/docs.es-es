---
title: "ServiceCredentials | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceCredentials
ServiceCredentials  
  
## Sintaxis  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## Métodos  
 La clase ServiceCredentials no define ningún método.  
  
## Propiedades  
 La clase ServiceCredentials posee las siguientes propiedades:  
  
### ClientCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.  
  
### IssuedTokenAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Los valores actuales de autenticación de token emitido para este servicio.  
  
### Del mismo nivel  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los extremos de transporte del mismo nivel.  
  
### SecureConversationAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica los valores de conversación seguros actuales.  
  
### ServiceCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El certificado asociado a este servicio.  
  
### UserNameAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Los valores de nombre de usuario\/contraseña para este servicio.  
  
### WindowsAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Los valores de autenticación de Windows para este servicio.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Description.ServiceCredentials>
---
title: "ClientCredentials | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ClientCredentials
ClientCredentials  
  
## Sintaxis  
  
```  
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## Métodos  
 La clase ClientCredentials no define ningún método.  
  
## Propiedades  
 La clase ClientCredentials tiene las propiedades siguientes:  
  
### ClientCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El certificado X.509 que utiliza el cliente para autenticarse en el servicio.  
  
### HttpDigest  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La credencial de Http Digest actual.  
  
### IssuedToken  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La dirección y el enlace del extremo utilizados para contactar con el servicio de tokens de seguridad local.  
  
### Del mismo nivel  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Las credenciales que el nodo del mismo nivel utiliza para autenticarse a otros nodos de la malla.  
  
### ServiceCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El certificado X.509 del servicio.  
  
### SupportInteractive  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si la credencial admite negociación interactiva.  
  
### UserName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre de usuario y la contraseña que el cliente utiliza para autenticarse al servicio.  
  
### Windows  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Las credenciales de Windows que el cliente utiliza para autenticarse al servicio.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Description.ClientCredentials>
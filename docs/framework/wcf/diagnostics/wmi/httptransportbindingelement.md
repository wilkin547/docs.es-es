---
title: "HttpTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# HttpTransportBindingElement
HttpTransportBindingElement  
  
## Sintaxis  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## Métodos  
 La clase HttpTransportBindingElement no define ningún método.  
  
## Propiedades  
 La clase HttpTransportBindingElement tiene las propiedades siguientes:  
  
### AllowCookies  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si el cliente acepta las cookies y las propaga en solicitudes futuras.  
  
### AuthenticationScheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema de autenticación usado para autenticar las solicitudes del cliente que está procesando un agente de escucha HTTP.  
  
### BypassProxyOnLocal  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si se omiten servidores proxy para direcciones locales.  
  
### HostNameComparisonMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si se usa el nombre del host para alcanzar el servicio al coincidir con el URI.  
  
### KeepAliveEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Cuando se habilita, las conexiones HTTP se mantienen vivas sin tener en cuenta el nivel de actividad.  
  
### MaxBufferSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El tamaño máximo del grupo de búferes.  
  
### ProxyAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un URI que contiene la dirección del proxy que utilizar para las solicitudes HTTP.  
  
### ProxyAuthenticationScheme  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El esquema de autenticación usado para autenticar las solicitudes del cliente que un proxy HTTP está procesando.  
  
### Dominio kerberos  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El dominio kerberos de autenticación.  
  
### TransferMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Un valor que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.  
  
### UnsafeConnectionNtlmAuthentication  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si la conexión compartida no segura está habilitada en el servidor.  
  
### UseDefaultWebProxy  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor que indica si se utiliza la configuración de proxy del equipo en lugar de la configuración específica del usuario.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
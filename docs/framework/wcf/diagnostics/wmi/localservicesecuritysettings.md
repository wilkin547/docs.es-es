---
title: "LocalServiceSecuritySettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# LocalServiceSecuritySettings
LocalServiceSecuritySettings  
  
## Sintaxis  
  
```  
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## Métodos  
 La clase LocalServiceSecuritySettings no define ningún método.  
  
## Propiedades  
 La clase LocalServiceSecuritySettings tiene las siguientes propiedades:  
  
### DetectReplays  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente.  
  
### InactivityTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de sesiones de seguridad pendientes que el servicio admite.  
  
### IssuedCookieLifetime  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración emitida a todas las nuevas cookies de seguridad.  
  
### MaxCachedCookies  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de cookies que pueden estar almacenadas en memoria caché.  
  
### MaxClockSkew  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación.  
  
### MaxPendingSessions  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de conexiones pendientes en el servicio.  
  
### MaxStatefulNegotiations  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número de negociaciones de seguridad que pueden estar activas de manera simultánea.  
  
### NegotiationTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración máxima para la fase de negociación de seguridad entre servidor y cliente.  
  
### ReconnectTransportOnFailure  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si las conexiones que usan mensajería WS\-Reliable intentan volverse a conectar después de los errores de transporte.  
  
### ReplayCacheSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número de valores de seguridad \(nonce\) almacenados en memoria caché usados para la detección de reproducción.  
  
### ReplayWindow  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración en la que los nonces de mensajes particulares son válidos.  
  
### SessionKeyRenewalInterval  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad.  
  
### SessionKeyRolloverInterval  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave.  
  
### TimestampValidityDuration  
 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan positivo que especifica la duración en la que una marca de tiempo es válida.  
  
## Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-------------------------------------|  
|Espacio de nombres|Se define en root\\ServiceModel|  
  
## Vea también  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
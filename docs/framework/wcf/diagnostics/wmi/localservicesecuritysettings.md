---
description: 'Más información acerca de: LocalServiceSecuritySettings'
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: f7220e8253c6ab218414c1be7ed90e5d593b4692
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743946"
---
# <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings

LocalServiceSecuritySettings  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
  
## <a name="methods"></a>Métodos  

 La clase LocalServiceSecuritySettings no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase LocalServiceSecuritySettings tiene las siguientes propiedades:  
  
### <a name="detectreplays"></a>DetectReplays  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de sesiones de seguridad pendientes que el servicio admite.  
  
### <a name="issuedcookielifetime"></a>IssuedCookieLifetime  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración emitida a todas las nuevas cookies de seguridad.  
  
### <a name="maxcachedcookies"></a>MaxCachedCookies  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de cookies que pueden estar almacenadas en memoria caché.  
  
### <a name="maxclockskew"></a>MaxClockSkew  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación.  
  
### <a name="maxpendingsessions"></a>MaxPendingSessions  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de conexiones pendientes en el servicio.  
  
### <a name="maxstatefulnegotiations"></a>MaxStatefulNegotiations  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número de negociaciones de seguridad que pueden estar activas de manera simultánea.  
  
### <a name="negotiationtimeout"></a>NegotiationTimeout  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración máxima para la fase de negociación de seguridad entre servidor y cliente.  
  
### <a name="reconnecttransportonfailure"></a>ReconnectTransportOnFailure  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si las conexiones que usan mensajería WS-Reliable intentan volverse a conectar después de los errores de transporte.  
  
### <a name="replaycachesize"></a>ReplayCacheSize  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número de valores de seguridad (nonce) almacenados en memoria caché usados para la detección de reproducción.  
  
### <a name="replaywindow"></a>ReplayWindow  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración en la que los nonces de mensajes particulares son válidos.  
  
### <a name="sessionkeyrenewalinterval"></a>SessionKeyRenewalInterval  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad.  
  
### <a name="sessionkeyrolloverinterval"></a>SessionKeyRolloverInterval  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave.  
  
### <a name="timestampvalidityduration"></a>TimestampValidityDuration  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 Un TimeSpan positivo que especifica la duración en la que una marca de tiempo es válida.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>

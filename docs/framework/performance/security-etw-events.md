---
title: Eventos ETW de seguridad
description: Comprender los eventos ETW de seguridad, que se generan durante la comprobación de nombre seguro y la comprobación de Authenticode en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474220"
---
# <a name="security-etw-events"></a>Eventos ETW de seguridad

Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a>Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1  
 En la tabla siguiente se muestra la palabra clave y el nivel. (Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0 x 400)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|Inicio de comprobación de nombre seguro.|  
|`StrongNameVerificationStop_V1`|182|Fin de comprobación de nombre seguro.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Marcas de verificación.|  
|ErrorCode|win:UInt32|Código de error HResult.|  
|FullyQualifiedAssemblyName|win:UnicodeString|Nombre completo del ensamblado.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a>Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0 x 400)|Informativo (4)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Inicio de la comprobación de Authenticode.|  
|`AuthenticodeVerificationStop_V1`|184|Fin de la comprobación de Authenticode.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Marcas de verificación.|  
|ErrorCode|win:UInt32|Código de error HResult.|  
|ModulePath|win:UnicodeString|Ruta de acceso del módulo.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## <a name="see-also"></a>Consulte también

- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)

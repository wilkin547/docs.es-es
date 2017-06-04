---
title: "Security ETW Events | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "security events [.NET Framework]"
  - "ETW, security events (CLR)"
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Security ETW Events
<a name="top"></a> Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.  
  
 Esta categoría consta de los siguientes eventos:  
  
-   [Eventos StrongNameVerificationStart\_V1 y StrongNameVerificationStop\_V1](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [Eventos AuthenticodeVerificationStart\_V1 y AuthenticodeVerificationStop\_V1](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## Eventos StrongNameVerificationStart\_V1 y StrongNameVerificationStop\_V1  
 En la tabla siguiente se muestra la palabra clave y el nivel. \(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)\).  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`SecurityKeyword` \(0 x 400\)|Informativo \(4\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`StrongNameVerificationStart_V1`|181|Inicio de comprobación de nombre seguro.|  
|`StrongNameVerificationStop_V1`|182|Fin de comprobación de nombre seguro.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|VerificationFlags|win:UInt32|Marcas de verificación.|  
|errorCode|win:UInt32|Código de error HResult.|  
|FullyQualifiedAssemblyName|win:UnicodeString|Nombre completo del ensamblado.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
 [Volver al principio](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## Eventos AuthenticodeVerificationStart\_V1 y AuthenticodeVerificationStop\_V1  
 En la tabla siguiente se muestra la palabra clave y el nivel.  
  
|Palabra clave para generar el evento|Nivel|  
|------------------------------------------|-----------|  
|`SecurityKeyword` \(0 x 400\)|Informativo \(4\)|  
  
 En la siguiente tabla se muestra la información del evento.  
  
|Evento|Id. de evento|Se genera cuando|  
|------------|-------------------|----------------------|  
|`AuthenticodeVerificationStart_V1`|183|Inicio de la comprobación de Authenticode.|  
|`AuthenticodeVerificationStop_V1`|184|Fin de la comprobación de Authenticode.|  
  
 En la siguiente tabla se muestran los datos del evento.  
  
|Nombre de campo|Tipo de datos|Descripción|  
|---------------------|-------------------|-----------------|  
|VerificationFlags|win:UInt32|Marcas de verificación.|  
|errorCode|win:UInt32|Código de error HResult.|  
|ModulePath|win:UnicodeString|Ruta de acceso del módulo.|  
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|  
  
## Vea también  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)
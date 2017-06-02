---
title: "System.ServiceModel.Channels.PeerNodeAuthenticationFailure | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# System.ServiceModel.Channels.PeerNodeAuthenticationFailure
El protocolo de enlace de seguridad con un vecino potencial no tuvo éxito.  
  
## Descripción  
 Este seguimiento se produce al intentar establecer una conexión segura con un vecino.Esto puede suceder debido a unas credenciales insuficientes o incorrectas.  
  
 PeerChannel reconoce un tipo de token único para una identificación fuerte, los certificados X.509, que proporcionan un modelo de identidad fuerte basados en el tipo de autenticación y autorización que se puede implementar.PeerChannel también proporciona compatibilidad para aplicaciones simples a través del uso de contraseñas.Las contraseñas solo se pueden utilizar para permitir la entrada a la sesión; no se pueden utilizar para realizar la autenticación de mensajes.Esto se debe a que es difícil e inadecuado utilizar un token simétrico que un grupo de iguales comparten para la autenticación de origen.  
  
## Solución de problemas  
 Asegúrese de que todos los vecinos tienen las credenciales de seguridad adecuadas.  
  
## Vea también  
 [Seguridad del canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)   
 [Seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Uso del seguimiento para solucionar problemas de su aplicación](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Administración y diagnóstico](../../../../../docs/framework/wcf/diagnostics/index.md)
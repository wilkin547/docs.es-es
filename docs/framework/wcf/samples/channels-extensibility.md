---
title: "Extensibilidad de los canales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Extensibilidad de los canales
Esta sección contiene ejemplos que muestran los canales personalizados.  
  
## En esta sección  
 [Canal local](../../../../docs/framework/wcf/samples/local-channel.md)  
 Muestra el canal local, un canal de transporte de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se utiliza para la comunicación dentro del mismo dominio de aplicación.  
  
 [Perfil seguro confiable](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 Muestra cómo crear [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y un perfil de protección confiable \(RSP, Reliable Secure Profile\).  
  
 [Distribuidor de canal personalizado](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 Muestra cómo crear la pila del canal de manera personalizada implementando <xref:System.ServiceModel.ServiceHostBase> directamente y cómo crear un distribuidor de canal personalizado en un entorno de host web.  
  
 [Canal de fragmentación](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 Muestra cómo limitar la cantidad de memoria que se usa para almacenar en búfer los mensajes grandes enviados con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Canal de confirmación de HTTP](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 Muestra un canal en niveles que cambia el modelo de mensajería unidireccional.  
  
 [HttpCookieSession](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 Muestra cómo generar un canal de protocolo personalizado para usar cookies de HTTP para la administración de sesiones.  
  
 [Interceptador de mensajes personalizados](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 Muestra cómo implementar un elemento de enlace personalizado que crea generadores de canales y agentes de escucha de canales para interceptar todos los mensajes entrantes y salientes en un punto concreto en la pila de tiempo de ejecución.
---
title: "Conversaciones y sesiones seguras | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# Conversaciones y sesiones seguras
Una característica de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es la capacidad de establecer sesiones seguras entre dos extremos que se autentican entre sí y están de acuerdo en un proceso de cifrado y firma digital.Por ejemplo, el extremo de servicio podría exigir a un extremo del cliente que envíe un token de seguridad basado en un certificado X.509 para su autenticación.Una vez autenticado el cliente, el extremo de servicio devuelve un token de contexto de seguridad \(SCT\) al cliente que se utiliza a continuación para proteger todos los mensajes subsiguientes dentro de la sesión.Al establecer esta sesión segura, se habilita el conjunto de mensajes que se intercambian entre los dos extremos para ser más eficaz, porque el SCT tiene una clave simétrica.Las claves asimétricas, en las que se basan los certificados X.509, requieren una potencia de cálculo bastante mayor que las claves simétricas cuando se genera una firma digital o se cifra un conjunto de datos.  
  
 La directiva de arranque \(definida en la sección 6.2.7 del estándar [WS\-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817)\) contiene las aserciones de seguridad de mensaje utilizadas para proteger el canal y autenticar el cliente antes del intercambio RST\/SCT y RSTR\/SCT.Determinados enlaces estándar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tienen una propiedad `Security.Message.EstablishSecurityContext` que controla si se utiliza o no una conversación protegida.Cuando se utilizan enlaces personalizados el arranque se indica mediante el anidamiento de elementos de enlaces de seguridad, bien a través de [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)<xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> en el archivo de configuración, bien llamando a en el código.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] sesiones, vea [Uso de sesiones](../../../../docs/framework/wcf/using-sessions.md).  
  
## Vea también  
 [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [Cómo crear un servicio que requiere sesiones](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
---
title: Conversaciones y sesiones seguras
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d519640c40daf248a01a19f0450f3aea8de6cc04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="secure-conversations-and-secure-sessions"></a>Conversaciones y sesiones seguras
Una característica de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es la capacidad de establecer sesiones seguras entre dos extremos que se autentican entre sí y están de acuerdo en un proceso de cifrado y firma digital. Por ejemplo, el extremo de servicio podría exigir a un extremo del cliente que envíe un token de seguridad basado en un certificado X.509 para su autenticación. Una vez autenticado el cliente, el punto de conexión de servicio devuelve un token de contexto de seguridad (SCT) al cliente que se utiliza a continuación para proteger todos los mensajes subsiguientes dentro de la sesión. Al establecer esta sesión segura, se habilita el conjunto de mensajes que se intercambian entre los dos extremos para ser más eficaz, porque el SCT tiene una clave simétrica. Las claves asimétricas, en las que se basan los certificados X.509, requieren una potencia de cálculo bastante mayor que las claves simétricas cuando se genera una firma digital o se cifra un conjunto de datos.  
  
 La directiva de arranque (definidos en la sección 6.2.7 de la [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) estándar) contiene las aserciones de seguridad de mensaje usan para proteger el canal y autenticar al cliente antes del intercambio SCT/RST y RSTR/SCT. Determinados enlaces estándar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tienen una propiedad `Security.Message.EstablishSecurityContext` que controla si se utiliza o no una conversación protegida. Al utilizar enlaces personalizados se indica el servicio de arranque por anidar elementos de enlace de seguridad, ya sea a través [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) en el archivo de configuración, o mediante una llamada a <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> en el código.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]las sesiones, consulte [mediante sesiones](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Vea también  
 [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Creación de un servicio que requiere sesiones](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)

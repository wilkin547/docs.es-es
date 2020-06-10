---
title: Conversaciones y sesiones seguras
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
ms.openlocfilehash: 3245c062db003cc387eff7af92fabe1554311c73
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590233"
---
# <a name="secure-conversations-and-secure-sessions"></a>Conversaciones y sesiones seguras
Una característica de Windows Communication Foundation (WCF) es la capacidad de establecer sesiones seguras entre dos puntos de conexión que se autentican entre sí y aceptan un cifrado y un proceso de firma digital. Por ejemplo, el punto de conexión de servicio podría exigir a un punto de conexión del cliente que envíe un token de seguridad basado en un certificado X.509 para su autenticación. Una vez autenticado el cliente, el extremo de servicio devuelve un token de contexto de seguridad (SCT) al cliente que se utiliza a continuación para proteger todos los mensajes subsiguientes dentro de la sesión. Al establecer esta sesión segura, se habilita el conjunto de mensajes que se intercambian entre los dos extremos para ser más eficaz, porque el SCT tiene una clave simétrica. Las claves asimétricas, en las que se basan los certificados X.509, requieren una potencia de cálculo bastante mayor que las claves simétricas cuando se genera una firma digital o se cifra un conjunto de datos.  
  
 La Directiva bootstrap (definida en la sección 6.2.7 del estándar [WS-SecurityPolicy](https://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/ws-securitypolicy-1.2-spec-os.html) ) contiene las aserciones de seguridad del mensaje que se usan para proteger el canal y autenticar el cliente antes del intercambio RST/SCT y RSTR/SCT. Algunos enlaces estándar de WCF tienen una `Security.Message.EstablishSecurityContext` propiedad que controla si se utiliza la conversación segura. Al utilizar enlaces personalizados, el bootstrap se indica mediante el anidamiento de los elementos de enlace de seguridad, ya sea a través [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) del archivo de configuración o mediante una llamada a <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> en el código.  
  
 Para obtener más información acerca de las sesiones, vea [usar sesiones](../using-sessions.md).  
  
## <a name="see-also"></a>Vea también

- [Sesiones, creación de instancias y simultaneidad](sessions-instancing-and-concurrency.md)
- [Procedimiento para crear un servicio que requiere sesiones](how-to-create-a-service-that-requires-sessions.md)

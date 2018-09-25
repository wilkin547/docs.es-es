---
title: Conversaciones y sesiones seguras
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
author: BrucePerlerMS
ms.openlocfilehash: 077f21f11fae9e91abe281778351954c80d9603b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47156252"
---
# <a name="secure-conversations-and-secure-sessions"></a>Conversaciones y sesiones seguras
Una característica de Windows Communication Foundation (WCF) es la capacidad de establecer sesiones seguras entre dos puntos de conexión que se autentican mutuamente y están de acuerdo en un proceso de firma digital y cifrado. Por ejemplo, el punto de conexión de servicio podría exigir a un punto de conexión del cliente que envíe un token de seguridad basado en un certificado X.509 para su autenticación. Una vez autenticado el cliente, el punto de conexión de servicio devuelve un token de contexto de seguridad (SCT) al cliente que se utiliza a continuación para proteger todos los mensajes subsiguientes dentro de la sesión. Al establecer esta sesión segura, se habilita el conjunto de mensajes que se intercambian entre los dos extremos para ser más eficaz, porque el SCT tiene una clave simétrica. Las claves asimétricas, en las que se basan los certificados X.509, requieren una potencia de cálculo bastante mayor que las claves simétricas cuando se genera una firma digital o se cifra un conjunto de datos.  
  
 La directiva de arranque (definida en la sección 6.2.7 del [WS-SecurityPolicy](https://go.microsoft.com/fwlink/?LinkId=99817) estándar) contiene las aserciones de seguridad de mensaje usadas para proteger el canal y autenticar el cliente antes del intercambio RST/SCT y RSTR/SCT. Determinados enlaces estándares de WCF tienen un `Security.Message.EstablishSecurityContext` se utiliza la propiedad que controla si secure conversation. Al utilizar los enlaces personalizados el arranque se indica mediante anidar elementos de enlace de seguridad, ya sea a través [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) en el archivo de configuración o mediante una llamada a <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> en el código.  
  
 Para obtener más información acerca de las sesiones, vea [mediante sesiones](../../../../docs/framework/wcf/using-sessions.md).  
  
## <a name="see-also"></a>Vea también  
 [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Creación de un servicio que requiere sesiones](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)

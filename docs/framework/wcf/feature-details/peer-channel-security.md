---
title: Seguridad del canal del mismo nivel
ms.date: 03/30/2017
ms.assetid: 2c59b164-3729-44f0-a967-f247c42de662
ms.openlocfilehash: f8015f41254d17f908f3665db65af3d82eaa2b6a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576088"
---
# <a name="peer-channel-security"></a>Seguridad del canal del mismo nivel
El canal del mismo nivel admite varios tipos de aplicaciones distribuidas que dependen de la mensajería entre varias entidades. Algunos ejemplos incluyen la distribución del contenido a escala de Internet, donde una fuente de confianza distribuye contenido (como multimedia o actualizaciones de software), un grupo de amigos intercambian música y fotos, o un equipo de compañeros de trabajo editan conjuntamente un documento. Cada uno de estos escenarios requiere un modelo de seguridad único. El modelo de seguridad del canal del mismo nivel está diseñado para resolver estos escenarios y proporciona un modelo de seguridad robusto para las necesidades respectivas de los diferentes modelos de identidad, autenticación y autorización.  
  
## <a name="security-scenarios"></a>Escenarios de seguridad  
 Un escenario de distribución del contenido requiere que cada destinatario del contenido identifique el origen del contenido. Debido a la naturaleza distribuida del escenario, no siempre es posible conocer y confiar en los intermediarios que procesan o interceptan los mensajes. Para mitigar eficazmente la amenaza de que un intermediario que no es de confianza pueda manipular los mensajes, las aplicaciones pueden proteger el mensaje en el remitente para que se detecte fácilmente cualquier intento de modificación. En este caso, dependiendo de la confidencialidad del contenido, el cifrado puede ser necesario.  
  
 Los escenarios de colaboración como la colaboración de documento en grupo requieren a menudo que cada miembro que participa en la sesión se identifique y autentique individualmente. Esto significa que un mecanismo para definir los grupos de usuarios y autenticar frente a esos grupos es necesario para tener una sesión segura. Es más, las aplicaciones podrían requerir el seguimiento de cada mensaje mediante la autenticación en el nivel de mensaje. En estos tipos de aplicaciones, el rendimiento se puede sacrificar a cambio de un esquema de seguridad más fuerte.  
  
 Una sesión de comunicación entre un grupo de usuarios fortuitos puede requerir modelos de seguridad informales, como el conocimiento de un secreto común en el grupo. Para estos tipos de aplicaciones, es más importante que el modelo de seguridad sea fácil de establecer y configurar que disponer de la forma más eficaz de autenticación o que proporcionar medidas de no rechazo. Para estos escenarios, un mecanismo de autenticación basado en contraseña ayuda a proteger la capa de comunicación al mismo tiempo que se continúa permitiendo la autenticación de mensajes. La seguridad basada en contraseña es la configuración predeterminada para el canal del mismo nivel.  
  
## <a name="token-types"></a>Tipos de token  
 El canal del mismo nivel reconoce un tipo de token único para una identificación segura, los certificados X.509, que proporcionan un modelo de identidad seguro basado en el tipo de autenticación y autorización que se puede implementar. La confidencialidad e integridad se proporcionan fácilmente mediante certificados. Sin embargo, los certificados X.509 pueden ser difíciles de utilizar e implementar.  
  
 El canal del mismo nivel también proporciona compatibilidad para aplicaciones simples a través del uso de contraseñas. Las aplicaciones pueden decidir establecer grupos del mismo nivel rápidos y simples basándose en una contraseña proporcionada. En este caso, un propietario de grupo decide y comunica la contraseña a los miembros. Cada miembro debe iniciar sesión con esta contraseña para poder participar en la sesión. Las contraseñas solo se pueden utilizar para permitir la entrada a la sesión; no se pueden utilizar para realizar la autenticación de mensajes. Esto se debe a que es difícil e inadecuado utilizar un token simétrico que un grupo de iguales comparten para la autenticación de origen.  
  
## <a name="security-model"></a>Modelo de seguridad  
 El canal del mismo nivel proporciona la capacidad de proteger los vínculos individuales que existen entre usuarios del mismo nivel. Esto significa que un mensaje nunca fluye en un vínculo no seguro (desde la perspectiva de la aplicación). Internamente, cada vínculo (un canal de transporte entre dos pares) se protege utilizando la seguridad de capa de transporte (TLS). Esto significa que cuando un remitente crea y envía un mensaje, se envía sobre transporte seguro a cada uno de sus pares inmediatos, que tienen acceso al mensaje y, a su vez, envían el mensaje a sus pares inmediatos a través de conexiones seguras. Esta seguridad solo funciona en el nivel de transporte y es independiente de los modelos de seguridad del mensaje.  
  
 El canal del mismo nivel también proporciona una manera de proteger los mensajes independientemente de la seguridad de transporte que se emplee. En este modelo, el mensaje se protege en el origen mediante el token de seguridad de origen, aunque actualmente solo se admiten los certificados X.509. El mensaje protegido se transmite a continuación a través de la red del mismo nivel. Cada par receptor puede comprobar la autenticidad del origen. Observe que se protege el mensaje para que los intermediarios no puedan manipularlo.  
  
 Para lograr la confidencialidad, las aplicaciones pueden emplear la seguridad de transporte mediante esquemas fuertes de pertenencia a grupos para evitar el acceso no autorizado a los mensajes.  
  
 El canal del mismo nivel no requiere un modelo de identidad concreto siempre y cuando la aplicación elija uno de los tipos de token admitidos. Las aplicaciones poseen completamente el ciclo de vida de estas identidades y decisiones de autenticación.  
  
## <a name="see-also"></a>Vea también

- [Protección de las aplicaciones de canal del mismo nivel](securing-peer-channel-applications.md)
- [Conceptos del canal del mismo nivel](peer-channel-concepts.md)
- [Creación de una aplicación de canal del mismo nivel](building-a-peer-channel-application.md)

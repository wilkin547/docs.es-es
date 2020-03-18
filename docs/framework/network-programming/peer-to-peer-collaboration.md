---
title: Colaboración de punto a punto
ms.date: 03/30/2017
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
ms.openlocfilehash: 7cf92f6bf3c269e584cb8b3cdcf910be5b89fd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047381"
---
# <a name="peer-to-peer-collaboration"></a>Colaboración de punto a punto

La función de las redes punto a punto es permitir que los equipos PC que existen en el perímetro de Internet puedan realizar tareas informáticas que van más allá de las simplemente basadas en el cliente. Los equipos PC modernos cuentan con un procesador muy rápido, una memoria amplia y un disco duro grande, si bien ninguna de estas características se usa en su totalidad para realizar las tareas informáticas habituales, como el correo electrónico y la exploración web. Estos equipos pueden actuar fácilmente como cliente y servidor (del mismo nivel) para varios tipos de aplicaciones.  
  
La infraestructura de colaboración de punto a punto es una implementación simplificada de la infraestructura punto a punto de Microsoft Windows que aprovecha el servicio Equipos a mi alrededor de Windows Vista y plataformas posteriores. Está concebida para aplicaciones habilitadas para el mismo nivel dentro de una subred para la que funciona el servicio Equipos a mi alrededor, aunque también puede ofrecer servicio a puntos de conexión de Internet o contactos. Incorpora el Administrador de contactos común que usan Live Messenger y otras aplicaciones compatibles con Live para determinar puntos de conexión de contacto, disponibilidad y presencia.  
  
## <a name="collaboration-applications"></a>Aplicaciones de colaboración

 Una aplicación de colaboración de punto a punto típica consta de los siguientes pasos:  
  
- Un elemento de mismo nivel determina la identidad de otro elemento de mismo nivel que está interesado en hospedar una sesión de colaboración.  
  
- Se envía una solicitud para hospedar una sesión y el host de mismo nivel acepta administrar la actividad de colaboración.  
  
- El host invita a los contactos en la subred (incluido el solicitante) a una sesión.  
  
- Todos los elementos de mismo nivel que quieran colaborar pueden agregar el host a sus administradores de contactos.  
  
- En el momento adecuado, la mayoría de los elementos de mismo nivel enviarán al host respuestas a la invitación, para aceptarla como para rechazarla.  
  
- Todos los equipos de mismo nivel que quieran colaborar se suscribirán al host de mismo nivel.  
  
- Mientras los equipos de mismo nivel están realizando su actividad de colaboración inicial, el host de mismo nivel puede agregar equipos de mismo nivel remotos a su administrador de contactos. También procesa todas las respuestas a la invitación para determinar quién la ha aceptado, quién la ha rechazado y quién no ha respondido.  Puede cancelar las invitaciones a los que no hayan respondido, o realizar otra actividad.  
  
- En este momento, el host de mismo nivel puede iniciar una sesión de colaboración con todos los equipos de mismo nivel invitados o registrar una aplicación con la infraestructura de colaboración.  Las aplicaciones de P2P usan la infraestructura de colaboración punto a punto y el espacio de nombres <xref:System.Net.PeerToPeer.Collaboration> para coordinar las comunicaciones de juegos, tablones de anuncios, conferencias y otras aplicaciones de presencia sin servidor.  
  
## <a name="peer-to-peer-networking-security"></a>Seguridad de redes punto a punto  

 En un dominio de Active Directory, los controladores de dominio proporcionan servicios de autenticación mediante Kerberos. En un entorno de equipos de mismo nivel sin servidor, estos deben proporcionar su propia autenticación. En las redes punto a punto, cualquier nodo puede actuar como una entidad de certificación, eliminando el requisito de un certificado raíz en el almacén raíz de confianza de cada elemento de mismo nivel. La autenticación se proporciona mediante certificados autofirmados, con formato de certificados X.509. Estos son los certificados que crea cada elemento de mismo nivel, lo que genera el par de claves pública y privada, y el certificado que se firma con la clave privada. El certificado autofirmado se usa para la autenticación y para proporcionar información sobre la entidad de mismo nivel. Al igual que la autenticación X.509, la autenticación de redes de mismo nivel se basa en una cadena de certificados que tiene su origen en una clave pública que sea de confianza.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.PeerToPeer.Collaboration>
- [Acerca del espacio de nombres System.Net.PeerToPeer.Collaboration](about-the-system-net-peertopeer-collaboration-namespace.md)

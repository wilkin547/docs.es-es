---
title: Acerca del espacio de nombres System.Net.PeerToPeer.Collaboration
ms.date: 03/30/2017
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
ms.openlocfilehash: 54eaf1a99aab8b1db61f4b46237d57104c9d1a44
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250715"
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a>Acerca del espacio de nombres System.Net.PeerToPeer.Collaboration

El espacio de nombres <xref:System.Net.PeerToPeer.Collaboration> proporciona clases y API que se usan para implementar actividades de colaboración de punto a punto mediante la infraestructura de colaboración de punto a punto.  
  
## <a name="classes"></a>Clases  

 Las clases principales que se usan en la implementación de una actividad de colaboración de punto a punto son las siguientes:  
  
- <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, que se puede usar para almacenar contactos de compañeros.  
  
- <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> en la que se colaborará (por ejemplo, un juego, un cliente de chat o una solución de conferencias).  
  
- Los elementos de mismo nivel que colaborarán en una actividad.  Estos elementos de mismo nivel se pueden representar como objetos <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> o <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint>.  
  
- La clase estática <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>, que especifica las aplicaciones que están disponibles y los elementos de mismo nivel que participan en ellas.  
  
 Los métodos <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> se usan para invitar a compañeros a una sesión de colaboración.  Un compañero que efectúa una llamada se puede suscribir a otro compañero para participar en eventos que indican actualizaciones en la información de presencia, de una aplicación o de un objeto, asociada a la sesión de colaboración. Las clases de presencia especifican si hay algún <xref:System.Net.PeerToPeer.Collaboration.Peer> disponible para la colaboración, mientras que la clase <xref:System.Net.PeerToPeer.Collaboration.PeerScope> se usa para especificar qué grado de participación se permite para un compañero: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (global), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe> (subred) o <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.  
  
 Una sesión de colaboración consta de cuatro pasos:  
  
- Descubrimiento. Descubra o publique aplicaciones, compañeros e información de presencia.  Por ejemplo, buscar a otras personas en la subred local que tengan instalados los mismos juegos.  
  
- Invitación. Envíe y acepte invitaciones seguras a los compañeros remotos para iniciar sesiones <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> o unirse a ellas.  
  
- Administración de contactos. Agregue compañeros que haya descubierto como contacto a un <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
- Comunicación. Una vez establecida la comunicación, use las API <xref:System.Net>, la API <xref:System.Net.PeerToPeer> o las clases de canales del mismo nivel de Windows Communication Foundation para las comunicaciones con varios participantes.  
  
 Por ejemplo, el compañero anfitrión inicia una sesión de colaboración y usa el método <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> para agregar a un compañero remoto y a uno de sus compañeros locales al administrador de contactos del compañero anfitrión.  Los tres usuarios participarán en su propia sesión de colaboración privada.  
  
 Aplicaciones P2P típicas: teleconferencias de colaboración con pizarra o para tomar notas, aplicaciones de chat sin servidor, anuncios interactivos y sesiones de juegos en línea.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.PeerToPeer.Collaboration>

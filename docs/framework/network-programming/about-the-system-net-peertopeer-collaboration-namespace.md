---
title: "Acerca del espacio de nombres System.Net.PeerToPeer.Collaboration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# Acerca del espacio de nombres System.Net.PeerToPeer.Collaboration
El espacio de nombres <xref:System.Net.PeerToPeer.Collaboration> proporciona clases y las API que se utilizan para implementar actividades del mismo nivel de colaboración mediante el Collaboration entre iguales Infrastructure.  
  
## Clases  
 Las clases principales utilizadas en la implementación de una actividad entre iguales de Collaboration son:  
  
-   <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, que se pueden utilizar para almacenar los contactos del mismo nivel.  
  
-   <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> en las que a colaborar, por ejemplo un juego, un cliente de chat, o una solución de comunicación.  
  
-   Los pares que colaborarán en una actividad.  Estos pares se pueden representar como <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, u objetos de <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> .  
  
-   La clase estática propio de <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> , que especifica qué aplicaciones están disponibles y qué pares participan en ellas.  
  
 Los métodos de <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> se utilizan para llamar en pares una sesión de colaboración.  Un par de llamada puede suscribirse a otro par para eventos que notifican actualizaciones de la aplicación, el objeto, o Información de presencia afiliada con la sesión de colaboración.  Las clases de la presencia especifican si <xref:System.Net.PeerToPeer.Collaboration.Peer> está disponible para la colaboración, y la clase de <xref:System.Net.PeerToPeer.Collaboration.PeerScope> se utiliza para especificar cuántas participación se permite un par: <xref:System.Net.PeerToPeer.Collaboration.PeerScope> \(global\), <xref:System.Net.PeerToPeer.Collaboration.PeerScope>, \(subred\) o <xref:System.Net.PeerToPeer.Collaboration.PeerScope>.  
  
 Comprenden una sesión de colaboración de cuatro pasos:  
  
-   Detección.  Detectar o publicar las aplicaciones, los pares, y la Información de presencia.  Por ejemplo, buscar a otras personas de la subred local que hacen los mismos conjuntos instalar.  
  
-   Tratar.  Envíe y acepte las invitaciones seguras para que el interlocutor remoto inicia o unirse a las sesiones de <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> .  
  
-   Póngase en contacto con administración.  Agregar detectó a pares como contacto a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
-   Comunicación.  Cuando la comunicación, utilice <xref:System.Net> API, <xref:System.Net.PeerToPeer> API, o Windows Communication Foundation Peer Channel ordena para las comunicaciones pluripartidistas.  
  
 Por ejemplo, el elemento host inicia una sesión de colaboración, y utiliza el método de <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> para agregar un interlocutor remoto y el que uno de sus nodos locales al administrador de contacto del par de host.  Los tres usuarios a participarán en su propia sesión privada de colaboración.  
  
 Las aplicaciones típicas de PROYECTOS son: llamadas de conferencia para nota\- tomar o whiteboarding cooperativo, aplicaciones serverless de chat, anuncios interactivos, y sesiones en línea del juego.  
  
## Vea también  
 <xref:System.Net.PeerToPeer.Collaboration>
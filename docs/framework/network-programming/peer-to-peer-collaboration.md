---
title: "Colaboraci&#243;n de punto a punto | Microsoft Docs"
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
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Colaboraci&#243;n de punto a punto
La conexión de red punto a punto es el uso de los equipos relativamente eficaces \(equipos\) que existen en el borde de internet para algo más que las tareas informáticas cliente\- basadas en.  \(PC\) Del personal moderno tiene un procesador muy rápido, memoria completa, y un disco duro grande, ninguno cuyo se usan completamente al realizar tareas informáticas comunes como correo electrónico y examinar web.  El equipo moderno con facilidad puede actuar como un cliente y servidor \(par\) para muchos tipos de aplicaciones.  
  
-   El Collaboration entre iguales Infrastructure es una implementación simplificada de Microsoft Windows Infrastructure entre iguales que aprovecha el servicio de Equipos a mi sobre en Windows Vista y plataformas posteriores.  Es más apropiado para aplicaciones par\- habilitadas en una subred para la que el servicio de Equipos a mi alrededor funcione, aunque puede mantener extremos o los contactos de Internet también.  En el administrador de contacto común utilizado por Live Messenger y otras aplicaciones Vivo\- con conocimiento pleno de determinar extremos, disponibilidad, y presencia contact.  
  
## Aplicaciones de colaboración  
 Una aplicación entre iguales típica de colaboración consta de los pasos siguientes:  
  
-   El par determina la identidad de un par que interesan en hospedar una sesión de colaboración  
  
-   Se envía una solicitud de hospedar una sesión, de algún modo, y el par de host acuerdan administrar actividad de colaboración.  
  
-   El host llama los contactos de la subred \(solicitante incluida\) a una sesión.  
  
-   Todos los pares que desean colaborar pueden agregar el host a los administradores de contacto.  
  
-   La mayoría de los pares envían respuestas de una llamada, están permitidos o rechazados, de nuevo el par host a su puntualmente.  
  
-   Todos los pares que desean colaborar suscribirán el par de host.  
  
-   Aunque los pares están realizando la actividad inicial de colaboración, el elemento host puede agregar a interlocutores remotos al administrador de contacto.  También procesa todas las respuestas de la llamada para determinar quién ha aceptado, que ha rechazado, y que no ha atendido.  Puede cancelar invitaciones a las que no han abiertas, o realizar alguna otra actividad.  
  
-   En este punto, el elemento host puede iniciar una sesión de colaboración con todos los pares llama, o registrar una aplicación con la infraestructura de colaboración.  Las aplicaciones entre PROYECTOS utilizan el Collaboration entre iguales Infraestructura y el espacio de nombres <xref:System.Net.PeerToPeer.Collaboration> para coordinar las comunicaciones para juegos, los boletines electrónicos, la comunicación, y otras aplicaciones serverless de la presencia.  
  
## Seguridad entre iguales de red  
 En un dominio de Active Directory, controladores de dominio proporcionan servicios de autenticación mediante Kerberos.  En un entorno del mismo nivel serverless, los pares deben proporcionar su propia autenticación.  Para la conexión de red entre iguales, cada nodo puede actuar como CA, quitar el requisito de un certificado raíz en el almacén de raíces de confianza de raíz de cada par.  La autenticación se proporciona utilizando los certificados autofirmados, con formato como certificados X.509.  Éstos son los certificados creados por cada par, que genera el par de claves pública y privada y el certificado que se firma utilizando la clave privada.  El certificado autofirmado se utiliza para la autenticación y proporcionar información sobre la entidad del mismo nivel.  Como la autenticación X.509, la autenticación del mismo nivel de red se basa en una cadena de certificados que seguimiento de traza a una clave pública que confirmada.  
  
## Vea también  
 <xref:System.Net.PeerToPeer.Collaboration>   
 [Acerca del espacio de nombres System.Net.PeerToPeer.Collaboration](../../../docs/framework/network-programming/about-the-system-net-peertopeer-collaboration-namespace.md)
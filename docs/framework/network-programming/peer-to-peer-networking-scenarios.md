---
title: "Escenarios de redes punto a punto | Microsoft Docs"
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
ms.assetid: d23b1a64-2e08-4014-882a-c1dd766bdcc2
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# Escenarios de redes punto a punto
La conexión de red punto a punto habilita o amplía los escenarios siguientes:  
  
## Comunicaciones en tiempo real \(RTC\)  
  
-   Mensajería instantánea de Serverless  
  
 RTC existe actual.  Los usuarios de sistemas pueden charlar y tener voz o conversaciones de vídeo con sus pares actual.  Sin embargo, muchos de los programas existentes y de los protocolos de comunicaciones confían en los servidores para funcionar.  Si va a combinar en una red inalámbrica ad hoc o es una parte de una red aislada, no puede utilizar estas funciones RTC.  La tecnología entre iguales permite la expansión de las tecnologías RTC en estos entornos de conexión de red adicionales.  
  
-   Servicio de contacto con contrincantes y gameplay en tiempo real  
  
 Similar a RTC, el juego en tiempo real de juego existe actual.  Hay muchos sitios Web\- basados de juego que abastecen a la comunidad de juego a través de internet.  Proporcionan la capacidad de buscar otros videojugadores con intereses similares y reproducir un juego juntos.  El problema es que los sitios de juego sólo existen en internet y se apropiados hacia el videojugador ávido que desea reproducir contra los mejores videojugadores universal.  Estos sitios siguen y proporcionan estadísticas para ayudar en el proceso.  Sin embargo, estos sitios no permiten que un videojugador configurar un juego ad hoc entre amigos en diferentes entornos de conexión de red.  La conexión de red punto a punto puede proporcionar esta capacidad.  
  
## Colaboración  
  
-   Áreas de trabajo del proyecto que resuelven un objetivo  
  
 Las aplicaciones compartidas en el área de trabajo permiten la creación de grupos de trabajo ad hoc y después permiten los propietarios de grupo de trabajo rellenen el área de trabajo compartida con las herramientas y la contenten que permitirá al grupo debe resolver un problema.  Esto podría incluir paneles de mensajes, las herramientas de productividad, y los archivos.  
  
-   Compartir archivos con otros  
  
 Un subconjunto de uso compartido del área de trabajo del proyecto es la capacidad de compartir los archivos.  Aunque esta capacidad existe actual con la versión actual de Windows, puede mejorar en la conexión de red punto a punto para crear contenido de archivo disponibles de una manera sencilla y fácil de usar.  Permitiendo acceso fácil a la riqueza increíble de contenido en el borde de internet o en entornos de computación ad hoc incrementa el valor de computación en red.  
  
-   Compartir experiencias  
  
 Con la conectividad inalámbricos cada vez más frecuente, la conexión de red de par\-a\- par permite que esté conectado en un grupo de pares y pueda compartir sus experiencias \(como una puesta de sol, un concierto de rock, o una pasan de vacaciones\) mientras se producen.  
  
## Distribución de contenido  
  
-   Mensajes de texto  
  
 La conexión de red punto a punto puede permitir la difusión de información basada en texto en forma de archivos o mensajes a un grupo de usuarios grande.  Un ejemplo es una lista de noticias.  
  
-   Audio y vídeo  
  
 La conexión de red entre iguales también puede permitir la difusión de información de audio o vídeo a un grupo de usuarios grande, como una reunión grande de concierto o de su empresa.  Para distribuir el contenido actual, debe configurar los servidores de alta capacidad obtener y distribuir la carga en cientos o a miles de usuarios.  Con conexión de red punto a punto, solo unos cuantos de pares obtendría realmente su contenido de servidores centralizados.  Estos pares inundarían esta información desproteger algunas más personas que la envían a otras, y así sucesivamente.  La carga de distribuir el contenido se distribuye a pares en nube.  Un par que desea recibir el contenido produce el par que distribuye más próximo y obtiene el contenido de ellos.  
  
-   Distribución de actualizaciones del producto  
  
 La conexión de red entre iguales también puede proporcionar un mecanismo eficaz para distribuir el software como actualizaciones del producto \(los actualizaciones de seguridad y los Service Pack\).  Un par que tiene una conexión a un servidor de distribución de software puede obtener la actualización del producto y difundirla a los otros miembros del grupo.  
  
## Procesamiento distribuido  
  
-   División y distribución de una tarea  
  
 Una tarea de computación grande se puede primero dividir en las tareas informáticas más pequeñas independientes apropiadas a los recursos de computación de un par.  Un par podría hacer dividir de la tarea de computación grande.  A continuación, la conexión de red punto a punto puede distribuir las tareas individuales a pares diferentes en el grupo.  Cada par realiza la tarea de software y sacar el resultado a un punto de acumulación centralizado.  
  
-   Agregación de los recursos del equipo  
  
 Otra manera de utilizar la conexión de red punto a punto para el procesamiento distribuido es ejecutar los programas de cada par que se ejecutan durante el tiempo de procesador inactivos y forma parte de una tarea de computación más grande que sea coordinada por un servidor central.  Agregando los procesadores de varios equipos, conexión de red punto a punto puede activar un grupo de equipos del mismo nivel en un procesador paralelo grande para las tareas informáticas grandes.  
  
## Vea también  
 <xref:System.Net.PeerToPeer.Collaboration>
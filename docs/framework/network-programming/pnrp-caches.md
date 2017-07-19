---
title: "Cach&#233;s PNRP | Microsoft Docs"
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
ms.assetid: 270068d9-1b6b-4eb9-9e14-e02326bb88df
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# Cach&#233;s PNRP
Las cachés de Peer Name Resolution Protocol \(PNRP\) son las colecciones locales de extremos del mismo nivel de algoritmos seleccionado que se mantienen en el mismo nivel.  
  
## Inicialización de caché de PNRP  
 Para inicializar la memoria caché de PNRP, o Peer Name Record Collection, cuando se inicia un nodo del mismo nivel, un nodo pueden utilizar los métodos siguientes:  
  
-   Las entradas persistentes de caché que se muestra cuando el nodo se cerró se cargan de almacenamiento en disco duro.  
  
-   Si una aplicación utiliza la infraestructura de colaboración entre PROYECTOS, la información de colaboración está disponible en el administrador de contacto para ese nodo.  
  
## Ajuste de escala Peer Name Resolution con una caché de Multi\- Nivel  
 Para mantener los tamaños de las cachés de PNRP los nodos pequeños, del mismo nivel utilizan la memoria caché de varios niveles, en la que cada nivel contiene un número máximo de entradas.  Cada nivel en caché representa una parte una décima parte menor del espacio del número de identificación de PNRP \(2<sup>256</sup>\).  El menor de la memoria caché contiene un id. localmente registrado de PNRP y otros id. de PNRP que está numéricamente cerca de.  Mientras un nivel de caché se rellena con un máximo de 20 entradas, se crea un nuevo nivel inferior.  El número máximo de niveles en la memoria caché está por orden de10registro \(número de Total de los id. de PNRP en la nube\).  Por ejemplo, para una nube global con 100 millones de id. de PNRP, hay no más de 8 \(\=log10\(100.000.000\)\) niveles en caché y un número similar de saltos para resolver un id. de PNRP durante la resolución de nombres.  Este mecanismo permite una tabla hash distribuida que un id. arbitrario de PNRP pueda resolver reenviando mensajes de solicitud de PNRP el par NeXT\- más próximo hasta que encuentre el par con el CPA correspondiente.  
  
 Para garantizar que la resolución puede completar, cada vez que un nodo agrega una entrada al menor de la memoria caché, inunda una copia de la entrada a todos los nodos en el último nivel de caché.  
  
 Las entradas de caché se actualizan con el tiempo.  Almacenar en memoria caché las entradas que están obsoletos se quitan de la memoria caché.  El resultado es que la tabla hash distribuida de id. de PNRP está basada en extremos activos, a diferencia de DNS en el que dirige los registros y el protocolo DNS no proporcionan ninguna garantía que el nodo asociado a la dirección es activamente en la red.  
  
## Otras cachés de PNRP  
 Otro almacén de datos persistente es una memoria caché local.  Además de los otros objetos necesarios para la actividad de PNRP, puede incluir los registros asociados a una sesión de nube o de colaboración de PNRP publicada y se sincronice con seguridad entre todos los miembros en la nube.  Esto almacén replicado representa la vista de los datos de grupo, que deben ser el mismo para todos los miembros del grupo.  Técnicamente, estos objetos no son registros por sí mismo, sino aplicación, presencia, y datos de objeto destinados para la caché local.  El uso de la nube de PNRP garantiza que los objetos están difundidos a todos los nodos de la sesión de colaboración o la nube de PNRP.  La replicación de registro entre los miembros de nube utiliza SSL para proporcionar el cifrado e integridad de datos.  
  
 Cuando un par participa una nube, automáticamente no reciben datos locales de caché de par de host al asociado; tienen que suscribirse al par de host para recibir las actualizaciones de la aplicación, la presencia, y datos de objeto.  Después de la sincronización inicial, los pares resincronizan periódicamente los almacenes replicados para garantizar que todos los miembros del grupo tienen siempre la misma vista.  La sesión o aplicaciones de colaboración dentro de la sesión de colaboración puede realizar la misma función.  
  
 Después de una sesión de colaboración haya comenzado a una nube, las aplicaciones pueden registrar los pares y empiece a publicar su información mediante seguridad definida por el ámbito de la nube.  Cuando un par participa una nube, los mecanismos de seguridad para la nube se aplican al par, proporcionando un ámbito en el que participar.  Los registros se podrán publicar con seguridad dentro del ámbito de la nube.  Observe que el ámbito de la nube puede no ser igual que el ámbito de aplicación de colaboración.  
  
 Los pares pueden registrar interés en recibir objetos de otros pares.  Cuando se actualiza un objeto, se notifica a la aplicación de la colaboración y el nuevo objeto se pasa a todos los suscriptores de la aplicación.  Por ejemplo, un par en una aplicación de chat de grupo puede registrar interés en recibir información de aplicación, que se enviarán todos los registros de chat como datos de la aplicación.  Esto permite supervisar la actividad de chat en la nube.  
  
## Vea también  
 <xref:System.Net.PeerToPeer>
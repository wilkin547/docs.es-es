---
title: Cachés PNRP
ms.date: 03/30/2017
ms.assetid: 270068d9-1b6b-4eb9-9e14-e02326bb88df
ms.openlocfilehash: 6f45b6d829867d830a9a10acf11e8456ba65d29e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263222"
---
# <a name="pnrp-caches"></a>Cachés PNRP

Las cachés del Protocolo de resolución de nombres de mismo nivel (PNRP) son colecciones locales de puntos de conexión de mismo nivel seleccionados de forma algorítmica y mantenidos en el elemento de mismo nivel.  
  
## <a name="pnrp-cache-initialization"></a>Inicialización de la caché de PNRP  

 Para inicializar la caché de PNRP, o la colección de registros de nombre de mismo nivel cuando se inicia un nodo de mismo nivel, un nodo puede usar los métodos siguientes:  
  
- Las entradas de caché persistente que se encontraban cuando se cerró el nodo se cargan desde el almacenamiento de disco duro.  
  
- Si una aplicación usa la infraestructura de colaboración P2P, la información de colaboración está disponible en el Administrador de contactos para ese nodo.  
  
## <a name="scaling-peer-name-resolution-with-a-multi-level-cache"></a>Escalado de la resolución de nombres de mismo nivel con una caché de varios niveles  

 Para mantener reducidos los tamaños de las caché de PNRP, los nodos de mismo nivel usan una caché de varios niveles en la que cada nivel contiene un número máximo de entradas. Cada nivel de la memoria caché representa una parte que es una décima parte menor del espacio de números de identificador PNRP (2<sup>256</sup>). El nivel más bajo en la memoria caché contiene un identificador PNRP registrado localmente y otros identificadores PNRP que están numéricamente cerca de él. Cuando un nivel de la memoria caché se rellena con un máximo de 20 entradas, se crea un nuevo nivel inferior. El número máximo de niveles en la memoria caché es del orden de log10(número total de identificadores PNRP en la nube). Por ejemplo, para una nube global con 100 millones de identificadores PNRP, no hay más de 8 (=log10(100,000,000)) niveles en la memoria caché y un número similar de saltos para resolver un identificador PNRP durante la resolución de nombres. Este mecanismo permite una tabla hash distribuida para la que se puede resolver un identificador PNRP arbitrario mediante el reenvío de mensajes de solicitud de PNRP al siguiente elemento de mismo nivel más cercano hasta que se encuentra el elemento de mismo nivel con la CPA correspondiente.  
  
 Para asegurarse de que se puede completar la resolución, cada vez que un nodo agrega una entrada al nivel más bajo de su caché, envía una copia de la entrada a todos los nodos en el último nivel de la caché.  
  
 Las entradas de caché se actualizan con el tiempo. Las entradas de caché que están obsoletas se quitan de la caché. El resultado es que la tabla hash distribuida de identificadores PNRP se basa en los puntos de conexión activos, a diferencia de DNS, donde los registros de dirección y el protocolo DNS no proporcionan ninguna garantía de que el nodo asociado con la dirección esté activo en la red.  
  
## <a name="other-pnrp-caches"></a>Otras cachés de PNRP  

 Otro almacén de datos persistente es la memoria caché local.  Además de los otros objetos necesarios para la actividad de PNRP, puede incluir los registros asociados con una sesión en la nube o de colaboración PNRP que se publica y se sincroniza entre todos los miembros de la nube de forma segura. Este almacén replicado representa la vista de los datos del grupo, que debe ser la misma para todos los miembros del grupo. Técnicamente, estos objetos no son registros por sí mismos, sino datos de aplicación, presencia y objeto destinados a una memoria caché local. El uso de la nube PNRP garantiza que los objetos se propaguen a todos los nodos de la sesión de colaboración o en la nube PNRP.  La replicación de registros entre los miembros de la nube usa SSL para proporcionar cifrado e integridad de datos.  
  
 Cuando un equipo de mismo nivel se une a una nube, no recibe automáticamente datos de la memoria caché local del host de mismo nivel al que se conecta; tiene que suscribirse al host de mismo nivel para recibir actualizaciones de los datos de aplicación, presencia y objeto. Después de la sincronización inicial, los equipos de mismo nivel resincronizan periódicamente sus almacenes replicados para garantizar que todos los miembros del grupo tengan la misma vista.  La sesión de colaboración o las aplicaciones dentro de la sesión de colaboración también pueden realizar la misma función.  
  
 Una vez iniciada una sesión de colaboración para una nube, las aplicaciones pueden registrar elementos de mismo nivel y empezar a publicar su información con la seguridad definida por el ámbito de nube. Cuando un equipo del mismo nivel se une a una nube, los mecanismos de seguridad de la nube se aplican a ese equipo, dándole un ámbito en el que participar.  Después, sus registros se pueden publicar de forma segura desde del ámbito de la nube. Tenga en cuenta que el ámbito de nube no puede ser el mismo que el ámbito de la aplicación de colaboración.  
  
 Los equipos de mismo nivel pueden registrar su interés por recibir objetos de otros equipos de mismo nivel. Cuando se actualiza un objeto, se notifica a la aplicación de colaboración y el nuevo objeto se pasa a todos los suscriptores de la aplicación. Por ejemplo, un equipo de mismo nivel en una aplicación de chat de grupo puede registrar su interés en recibir información de la aplicación, que se enviará todos los registros de chat como datos de la aplicación.  Esto le permite supervisar la actividad de chat dentro de la nube.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.PeerToPeer>

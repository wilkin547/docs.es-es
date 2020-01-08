---
title: Trabajar con NAT y firewalls
ms.date: 03/30/2017
helpviewer_keywords:
- firewalls [WCF]
- NATs [WCF]
ms.assetid: 74db0632-1bf0-428b-89c8-bd53b64332e7
ms.openlocfilehash: bfbff63c8c2cdb76d5f6d84424a9b03233744dae
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347106"
---
# <a name="working-with-nats-and-firewalls"></a>Trabajar con NAT y firewalls
Frecuentemente, el cliente y servidor de una conexión de red no tienen una ruta de acceso directa y abierta para la comunicación. Los paquetes se filtran, enrutan, analizan y transforman tanto en los equipos de extremo como en equipos intermedios de la red. Las traducciones de direcciones de red (NATs) y los firewalls son ejemplos comunes de aplicaciones intermedias que pueden participar en la comunicación de redes.  
  
 Los transportes de Windows Communication Foundation (WCF) y los patrones de intercambio de mensajes (MEP) reaccionan de forma diferente a la presencia de NAT y firewalls. En este tema se describe cómo las NAT y los firewalls funcionan en topologías de redes comunes. Se proporcionan recomendaciones para combinaciones específicas de transportes y MEP de WCF que ayudan a hacer que sus aplicaciones sean más sólidas para NAT y firewalls en la red.  
  
## <a name="how-nats-affect-communication"></a>Cómo afectan las NAT a la comunicación  
 NAT se creó para permitir a varios equipos compartir una dirección IP externa única. Una NAT de reasignación de puertos asigna una dirección IP interna y un puerto para una conexión a una dirección IP externa con un nuevo número de puerto. El nuevo número de puerto le permite a la NAT correlacionar el tráfico del retorno con la comunicación original. Muchos usuarios domésticos tienen una dirección IP que solo es enrutable de manera privada y confían en una NAT para que proporcione el enrutamiento global de paquetes.  
  
 Una NAT no proporciona un límite de seguridad. Sin embargo, las configuraciones NAT comunes evitan que se direccionen los equipos internos directamente. Esto protege los equipos internos de algunas conexiones no deseadas y dificulta la escritura de aplicaciones de servidor que deben devolver de forma asincrónica datos al cliente. La NAT reescribe las direcciones en paquetes para hacer parecer que se están originando conexiones en el equipo NAT. Esto hace que el servidor obtenga un error al intentar abrir una conexión de vuelta al cliente. Si el servidor utiliza la dirección percibida del cliente, se produce un error porque no se puede enrutar la dirección del cliente públicamente. Si el servidor utiliza la dirección NAT, no puede conectarse porque ninguna aplicación está realizando escuchas en ese equipo.  
  
 Algunas NAT admiten la configuración de reglas de reenvío para permitir a los equipos externos que se conecten a un equipo interno determinado. Las instrucciones para configurar las reglas de reenvío varían entre NAT diferentes y no se recomienda para la mayoría de las aplicaciones el pedir a los usuarios finales que cambien su configuración NAT. Muchos usuarios finales no pueden o no quieren cambiar su configuración de NAT para una aplicación determinada.  
  
## <a name="how-firewalls-affect-communication"></a>Cómo afectan los firewalls a la comunicación  
 Un *firewall* es un software o dispositivo de hardware que aplica reglas al tráfico que pasa a través de para decidir si permitir o denegar el paso. Puede configurar los firewalls para examinar secuencias de tráfico entrantes o salientes. El firewall proporciona un límite de seguridad para la red en el borde de la red o en el host del extremo. Los usuarios de empresas han mantenido tradicionalmente sus servidores tras un firewall para evitar ataques malintencionados. Desde la introducción del firewall personal en [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], el número de usuarios domésticos tras un firewall también ha aumentado en gran medida. Esto hace probable que uno o ambos extremos de una conexión tengan un firewall que examine los paquetes.  
  
 Los firewalls varían en gran medida en cuanto a su complejidad y capacidad para examinar los paquetes. Los firewalls simples aplican reglas basadas en las direcciones de origen y destino y los puertos en los paquetes. Los firewalls inteligentes también pueden examinar el contenido de paquetes para tomar decisiones. Estos firewalls vienen en muchas configuraciones diferentes y se utilizan a menudo para aplicaciones especializadas.  
  
 Una configuración común para un firewall del usuario doméstico consiste en prohibir las conexiones entrantes a menos que se haya realizado una conexión de salida previamente a ese equipo. Una configuración común para un firewall de usuario empresarial consiste en prohibir las conexiones entrantes en todos los puertos exceptuando un grupo identificado específicamente. Un ejemplo es un firewall que prohíbe las conexiones en todos los puertos salvo el puerto 80 y 443 para proporcionar servicio HTTP y HTTPS. Los firewalls administrados existen tanto para usuarios domésticos como para usuarios empresariales, y permiten a un usuario o proceso de confianza del equipo cambiar la configuración del firewall. Los firewalls administrados son más comunes para usuarios domésticos donde no hay ninguna directiva corporativa que controle el uso de la red.  
  
## <a name="using-teredo"></a>Uso de Teredo  
 Teredo es una tecnología de transición de IPv6 que habilita la direccionabilidad directa de equipos detrás de una NAT. Teredo se basa en el uso de un servidor que se puede enrutar de manera pública y global para anunciar conexiones potenciales. El servidor de Teredo da al servidor y cliente de la aplicación un punto de reunión común en el que pueden intercambiar información de conexión. Los equipos solicitan a continuación una dirección Teredo temporal y los paquetes se pasan mediante túneles a través de la red existente. La compatibilidad con Teredo en WCF requiere la habilitación de la compatibilidad con IPv6 y Teredo en el sistema operativo. [!INCLUDE[wxp](../../../../includes/wxp-md.md)] y los sistemas operativos posteriores admiten Teredo. Los sistemas operativos Windows Vista y versiones posteriores admiten IPv6 de forma predeterminada y solo requieren que el usuario habilite Teredo. [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] y Windows Server 2003 requieren que el usuario habilite IPv6 y Teredo. Para obtener más información, vea [información general sobre Teredo](https://go.microsoft.com/fwlink/?LinkId=87571).  
  
## <a name="choosing-a-transport-and-message-exchange-pattern"></a>Elección de un patrón de intercambio de mensajes y transporte  
 La selección de un transporte y MEP es un proceso de tres pasos:  
  
1. Analice la direccionabilidad de los equipos de extremo. Los servidores de empresas tienen normalmente direccionabilidad directa, mientras que los usuarios finales tienen normalmente la direccionabilidad bloqueada mediante NAT. Si ambos puntos de conexión están detrás de una NAT, como en escenarios punto a punto entre usuarios finales, podría necesitar una tecnología como Teredo para proporcionar direccionabilidad.  
  
2. Analice el protocolo y las restricciones de puertos de los equipos de puntos de conexión. Los servidores de empresa están generalmente detrás de firewalls fuertes que bloquean muchos puertos. Sin embargo, el puerto 80 se abre con frecuencia para permitir el tráfico HTTP, y el puerto 443 se abre para permitir el tráfico HTTPS. Es menos probable que los usuarios finales tengan restricciones de puertos, pero puede que estén detrás de un firewall que solo permita conexiones de salida. Algunos firewalls permiten la administración mediante aplicaciones en el extremo para abrir conexiones de manera selectiva.  
  
3. Calcule los transportes y MEP que permiten la direccionabilidad y las restricciones de puertos de la red.  
  
 Una topología común para las aplicaciones cliente-servidor consiste en tener clientes que estén detrás de un NAT sin Teredo con un firewall solo de salida y un servidor que sea direccionable de manera directa con un firewall fuerte. En este escenario, el transporte TCP con un MEP dúplex y un transporte HTTP con un MEP de solicitud-respuesta funcionan bien. Una topología común para las aplicaciones punto a punto consiste en tener ambos extremos detrás de NAT y firewalls. En este escenario y en escenarios donde la topología de red sea desconocida, considere las recomendaciones siguientes:  
  
- No utilice transportes duales. Un transporte dual abre más conexiones, lo que reduce la oportunidad de realizar correctamente una conexión.  
  
- Permita establecer canales secundarios a través de la conexión originaria. Utilizar canales secundarios, como en TCP dúplex, abre menos conexiones, lo que aumenta la oportunidad de realizar correctamente una conexión.  
  
- Emplee un servicio alcanzable para registrar puntos de conexión o la retransmisión de tráfico. El uso de un servicio de conexión alcanzable globalmente, como un servidor Teredo, aumenta en gran medida la probabilidad de realizar correctamente una conexión cuando la topología de red es restrictiva o desconocida.  
  
 En las tablas siguientes se examinan los MEPS unidireccionales, de solicitud-respuesta y dúplex, y el TCP estándar, TCP con Teredo, y los transportes HTTP estándar y dual en WCF.  
  
|Direccionabilidad|Servidor directo|Servidor directo con transversal NAT|Servidor NAT|Servidor NAT con transversal NAT|  
|--------------------|-------------------|--------------------------------------|----------------|-----------------------------------|  
|Cliente directo|Cualquier transporte y MEP.|Cualquier transporte y MEP.|No se admite.|No se admite.|  
|Cliente directo con transversal NAT|Cualquier transporte y MEP.|Cualquier transporte y MEP.|No se admite.|TCP con Teredo y cualquier MEP. Windows Vista tiene una opción de configuración de todo el equipo para admitir HTTP con Teredo.|  
|NAT cliente|Cualquier transporte no dual y MEP. Un MEP dúplex requiere transporte TCP.|Cualquier transporte no dual y MEP. Un MEP dúplex requiere transporte TCP.|No se admite.|No se admite.|  
|NAT cliente con transversal NAT|Cualquier transporte no dual y MEP. Un MEP dúplex requiere transporte TCP.|Todos menos HTTP dual y cualquier MEP. Un MEP dúplex requiere transporte TCP. El transporte TCP dual necesita Teredo. Windows Vista tiene una opción de configuración de todo el equipo para admitir HTTP con Teredo.|No se admite.|TCP con Teredo y cualquier MEP. Windows Vista tiene una opción de configuración de todo el equipo para admitir HTTP con Teredo.|  
  
|Restricciones del firewall|Servidor abierto|Servidor con firewall administrado|Servidor con firewall solo HTTP|Servidor con firewall solo de salida|  
|---------------------------|-----------------|----------------------------------|-------------------------------------|-----------------------------------------|  
|Cliente abierto|Cualquier transporte y MEP.|Cualquier transporte y MEP.|Cualquier transporte HTTP y MEP.|No se admite.|  
|Cliente con firewall administrado|Cualquier transporte no dual y MEP. Un MEP dúplex requiere transporte TCP.|Cualquier transporte no dual y MEP. Un MEP dúplex requiere transporte TCP.|Cualquier transporte HTTP y MEP.|No se admite.|  
|Cliente con firewall solo HTTP|Cualquier transporte HTTP y MEP.|Cualquier transporte HTTP y MEP.|Cualquier transporte HTTP y MEP.|No se admite.|  
|Cliente con firewall solo de salida|Cualquier transporte no dual y MEP. Un MEP dúplex requiere transporte TCP.|Cualquier transporte no dual y MEP. Un MEP dúplex requiere transporte TCP.|Cualquier transporte HTTP y cualquier MEP no dúplex.|No se admite.|

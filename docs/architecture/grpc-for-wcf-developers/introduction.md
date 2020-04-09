---
title: Introducción - gRPC para desarrolladores de WCF
description: Introducción
ms.date: 09/02/2019
ms.openlocfilehash: 41f470eb02a77b1b6a26a7d4c2ca347ad07d828d
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988939"
---
# <a name="introduction"></a>Introducción

Ayudar a las máquinas a comunicarse entre sí ha sido una de las principales preocupaciones de la era digital. En particular, hay un esfuerzo continuo para determinar el mecanismo de comunicación remota óptimo que se adapte a las demandas de interoperabilidad de la infraestructura actual. Como puede imaginar, ese mecanismo cambia a medida que evolucionan las demandas o la infraestructura.

El lanzamiento de .NET Core 3.0 marca un cambio en la forma en que Microsoft ofrece soluciones de comunicación remota a los desarrolladores que desean ofrecer servicios en una amplia gama de plataformas. .NET Core no ofrece Windows Communication Foundation (WCF) de forma inmediata, pero, con el lanzamiento de ASP.NET Core 3.0, proporciona funcionalidad gRPC integrada.

gRPC es un marco popular en la comunidad de software más amplia. Lo usan los desarrolladores en muchos lenguajes de programación para escenarios RPC modernos. La comunidad y el ecosistema son vibrantes y activos. Se está agregando compatibilidad con el protocolo gRPC a componentes de infraestructura como Kubernetes, mallas de servicio, equilibradores de carga y mucho más. Estos factores, junto con su rendimiento, eficiencia y compatibilidad multiplataforma, hacen de gRPC una opción natural para nuevas aplicaciones y aplicaciones WCF que se mueven a .NET Core.

## <a name="history"></a>Historial

El principio fundamental de una red informática como nada más que un grupo de ordenadores intercambiando datos entre sí para lograr un conjunto de tareas interrelacionadas no ha cambiado desde su creación. Pero la complejidad, la escala y las expectativas han crecido exponencialmente.  

Durante la década de 1990, se hizo hincapié principalmente en la mejora de las redes internas que utilizaban el mismo lenguaje y plataformas. TCP/IP se convirtió en el estándar de oro para este tipo de comunicación.

El enfoque pronto se centró en la mejor manera de optimizar la comunicación en múltiples plataformas promoviendo un enfoque independiente del lenguaje. La arquitectura orientada a servicios (SOA) proporciona una estructura para acoplar libremente una amplia colección de servicios que se pueden proporcionar a una aplicación.

El desarrollo de *los servicios web* se produjo cuando todas las plataformas principales podían acceder a Internet, pero todavía no podían interactuar entre sí. Los servicios web tienen estándares y protocolos abiertos, que incluyen:

- XML para etiquetar y codificar datos.
- Protocolo simple de acceso a objetos (SOAP) para transferir datos.
- Lenguaje de definición de servicios web (WSDL) para describir y conectar servicios web a aplicaciones cliente.
- Descripción universal, detección e integración (UDDI) para que otros servicios puedan detectar servicios web.

SOAP define las reglas por las que los elementos distribuidos de una aplicación pueden comunicarse entre sí, incluso si están en plataformas diferentes. SOAP se basa en XML, por lo que es legible por humanos. El sacrificio por hacer QUE SOAP se entienda fácilmente es el tamaño; Los mensajes SOAP son más grandes que los mensajes de protocolos comparables. SOAP se diseñó para dividir las aplicaciones monolíticas en forma multicomponente sin perder seguridad ni control. Así que WCF se diseñó para trabajar con ese tipo de sistema, a diferencia de gRPC, que comenzó como un sistema distribuido. WCF abordó algunas de estas limitaciones mediante el desarrollo y la documentación de protocolos de extensión propietarios para la pila SOAP, pero a costa de la falta de soporte de otras plataformas.

Windows Communication Foundation es un marco para crear servicios. Fue diseñado a principios de la década de 2000 para ayudar a los desarrolladores que utilizan SOA temprano para administrar las complejidades de trabajar con SOAP. Aunque quita el requisito para que los desarrolladores escriban sus propios protocolos SOAP, WCF sigue utilizando SOAP para habilitar la interoperabilidad con otros sistemas. WCF también se diseñó para ofrecer soluciones a través de varios protocolos (HTTP/1.1, Net.TCP, etc.).

## <a name="microservices"></a>Microservicios

En las arquitecturas de microservicios, las aplicaciones grandes se crean como una colección de servicios modulares más pequeños. Cada componente realiza una tarea o proceso específico, y los componentes están diseñados para funcionar de forma interoperable, pero se pueden aislar según sea necesario.

Las ventajas de los microservicios incluyen:

- Los cambios y las actualizaciones se pueden gestionar de forma independiente.
- El control de errores se vuelve más eficaz porque los problemas se pueden rastrear a servicios específicos que, a continuación, se aíslan, se reconstruyen, se prueban y se vuelven a implementar independientemente de los demás servicios.
- La escalabilidad se puede limitar a instancias o servicios específicos en lugar de a toda la aplicación.
- El desarrollo puede ocurrir en varios equipos, con menos fricción que ocurre cuando muchos equipos trabajan en un solo código base.

El avance hacia el aumento de la virtualización, la computación en la nube, los contenedores y el Internet de las cosas ha contribuido al aumento continuo de los microservicios. Pero los microservicios no están sin sus desafíos. La infraestructura fragmentada/descentralizada puso más énfasis en la necesidad de simplicidad y rapidez al comunicarse entre servicios. Esto a su vez llamó la atención sobre la naturaleza a veces laboriosa y contorsionada de SOAP.

Fue en este entorno que se lanzó gRPC, 10 años después de que Microsoft lanzara por primera vez WCF. Evolucionó directamente a partir de la infraestructura interna RPC (Stubby) de Google, gRPC nunca se basó en los mismos estándares y protocolos que habían informado los parámetros de muchos RPC anteriores. Y gRPC sólo se basó en HTTP/2. Es por eso que podría aprovechar las nuevas capacidades que proporciona el protocolo de transporte avanzado. En particular, la transmisión bidireccional, la mensajería binaria y la multiplexación.

## <a name="about-this-guide"></a>Acerca de esta guía

Esta guía cubre las características clave de gRPC. Los primeros capítulos toman una mirada de alto nivel a las características principales de WCF y compararlas con las de gRPC. Identifica dónde hay correlaciones directas entre WCF y gRPC y también donde gRPC ofrece una ventaja. Cuando no hay correlación entre WCF y gRPC, o cuando gRPC no es capaz de ofrecer una solución equivalente a WCF, esta guía sugerirá soluciones alternativas o a dónde ir para obtener más información.

Mediante un conjunto de aplicaciones WCF de ejemplo, el capítulo 5 es una mirada profunda a la conversión de los principales tipos de servicio WCF (solicitud simple-respuesta, unidireccional y streaming) a sus equivalentes en gRPC.

La sección final del libro analiza cómo obtener lo mejor de gRPC en la práctica. Esta sección incluye información sobre el uso de herramientas adicionales, como contenedores Docker o Kubernetes, para aprovechar la eficiencia de gRPC. También incluye una visión detallada de la supervisión con registro, métricas y seguimiento distribuido.

## <a name="who-this-guide-is-for"></a>Destinatarios de esta guía

Esta guía se escribió para los desarrolladores que trabajan en .NET Framework o .NET Core que han utilizado WCF y que buscan migrar sus aplicaciones a un entorno RPC moderno para .NET Core 3.0 y versiones posteriores. La guía también podría ser útil de forma más general para los desarrolladores que actualizan o consideran la actualización a .NET Core 3.0 y que desean usar las herramientas gRPC integradas.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](grpc-overview.md)

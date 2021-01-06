---
title: 'Introducción: gRPC para desarrolladores de WCF'
description: Introducción
ms.date: 12/15/2020
ms.openlocfilehash: f85d174da6d6493e6f406f132f2ffb773cbcc33d
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938603"
---
# <a name="introduction"></a>Introducción

Ayudar a las máquinas a comunicarse entre sí ha sido una de las principales preocupaciones de la era digital. En concreto, hay un esfuerzo continuo para determinar el mecanismo de comunicación remota óptimo que se adaptará a las demandas de interoperabilidad de la infraestructura actual. Como puede imaginar, ese mecanismo cambia a medida que evolucionan las demandas o la infraestructura.

La versión de .NET Core 3,0 marca un cambio en la forma en que Microsoft ofrece soluciones de comunicación remota a los desarrolladores que quieren ofrecer servicios a través de una variedad de plataformas. .NET Core y versiones posteriores no ofrecen Windows Communication Foundation (WCF) de un solo cuadro, sino que con el lanzamiento de ASP.NET Core 3,0, proporciona funcionalidad gRPC integrada.

gRPC es un marco popular en la mayor comunidad de software. Lo usan los desarrolladores en muchos lenguajes de programación para los escenarios de RPC modernos. La comunidad y el ecosistema son vibrante y activo. La compatibilidad con el protocolo gRPC se agrega a componentes de infraestructura como Kubernetes, mallas de servicio, equilibradores de carga, etc. Estos factores, junto con el rendimiento, la eficacia y la compatibilidad entre plataformas, hacen que gRPC sea una opción natural para aplicaciones nuevas y aplicaciones WCF que se mueven a .NET.

## <a name="history"></a>Historial

El principio fundamental de una red de equipos como nada más que un grupo de equipos que intercambian datos entre sí para lograr un conjunto de tareas interrelacionadas no ha cambiado desde su inicio. Pero la complejidad, la escala y las expectativas han crecido exponencialmente.

Durante los años noventa, el énfasis era principalmente en mejorar las redes internas que usaban el mismo lenguaje y plataformas. TCP/IP se convirtió en el estándar Gold para este tipo de comunicación.

El enfoque se centra pronto en la mejor forma de optimizar la comunicación entre varias plataformas mediante la promoción de un enfoque independiente del lenguaje. La arquitectura orientada a servicios (SOA) proporciona una estructura para el acoplamiento flexible de una amplia colección de servicios que se podrían proporcionar a una aplicación.

El desarrollo de *servicios web* se produjo cuando todas las plataformas principales podían tener acceso a Internet, pero siguen sin poder interactuar entre sí. Los servicios Web de tienen estándares y protocolos abiertos, entre los que se incluyen:

- XML para etiquetar y codificar datos.
- Protocolo simple de acceso a objetos (SOAP) para transferir datos.
- Lenguaje de definición de servicios web (WSDL) para describir y conectar los servicios web a las aplicaciones cliente.
- Universal Description, Discovery, and Integration (UDDI) para que otros servicios puedan detectar los servicios Web.

SOAP define las reglas por las que los elementos distribuidos de una aplicación pueden comunicarse entre sí, aunque estén en distintas plataformas. SOAP se basa en XML, por lo que es legible. El sacrificio para facilitar la comprensión de SOAP es el tamaño; Los mensajes SOAP son más grandes que los mensajes en protocolos comparables. SOAP se diseñó para dividir las aplicaciones monolíticas en un formato multicomponente sin perder seguridad ni control. De este modo, WCF se diseñó para funcionar con ese tipo de sistema, a diferencia de gRPC, que comenzó como sistema distribuido. WCF solucionó algunas de estas limitaciones al desarrollar y documentar protocolos de extensión propietarios para la pila SOAP, pero a costa de una falta de compatibilidad de otras plataformas.

Windows Communication Foundation es un marco de trabajo para la creación de servicios. Se diseñó en el 2000s temprano para ayudar a los desarrolladores a usar SOA temprano a administrar las complejidades del trabajo con SOAP. Aunque elimina el requisito de que los desarrolladores escriban sus propios protocolos SOAP, WCF sigue utilizando SOAP para habilitar la interoperabilidad con otros sistemas. WCF también se ha diseñado para ofrecer soluciones en varios protocolos (HTTP/1.1, net. TCP, etc.).

## <a name="microservices"></a>Microservicios

En las arquitecturas de microservicios, las aplicaciones de gran tamaño se compilan como una colección de servicios modulares más pequeños. Cada componente realiza una tarea o proceso específico y los componentes están diseñados para funcionar de forma internecesaria, pero se pueden aislar según sea necesario.

Entre las ventajas de los microservicios se incluyen:

- Los cambios y las actualizaciones se pueden administrar de forma independiente.
- El control de errores es más eficaz, ya que se puede realizar un seguimiento de los problemas a los servicios específicos que se aíslan, se vuelven a compilar, probar y volver a implementar independientemente de los demás servicios.
- La escalabilidad se puede limitar a instancias o servicios específicos en lugar de a toda la aplicación.
- El desarrollo puede producirse en varios equipos, con menos fricción de lo que ocurre cuando muchos equipos trabajan en un solo código base.

El avance hacia el aumento de la virtualización, la informática en la nube, los contenedores y el Internet de las cosas ha contribuido al aumento continuo de los microservicios. Sin embargo, los microservicios no tienen sus desafíos. La infraestructura fragmentada o descentralizada pone más énfasis en la necesidad de simplicidad y velocidad al comunicarse entre los servicios. Esto, a su vez, ha captado la atención a la naturaleza de SOAP a veces laboriosa y con responsabilidad.

Se encontraba en este entorno en el que se lanzó gRPC, 10 años después de que Microsoft lanzó por primera vez WCF. Evolucionó directamente de la RPC de la infraestructura interna de Google (Stubby), gRPC nunca se basó en los mismos estándares y protocolos que habían informado de los parámetros de muchas RPC anteriores. Y gRPC solo se basaba en HTTP/2. Por eso podría basarse en las nuevas capacidades que el protocolo de transporte avanzado proporcionó. En concreto, streaming bidireccional, mensajería binaria y multiplexación.

## <a name="about-this-guide"></a>Acerca de esta guía

En esta guía se tratan las principales características de gRPC. En los capítulos iniciales se ofrece una visión general de las principales características de WCF y se comparan con las de gRPC. Identifica dónde hay correlaciones directas entre WCF y gRPC y también donde gRPC ofrece una ventaja. Cuando no hay ninguna correlación entre WCF y gRPC, o cuando gRPC no puede ofrecer una solución equivalente a WCF, en esta guía se sugieren soluciones alternativas o dónde se puede obtener más información.

Con un conjunto de aplicaciones WCF de ejemplo, el capítulo 5 es una visión detallada de la conversión de los tipos principales de servicio WCF (solicitud-respuesta simple, unidireccional y transmisión por secuencias) a sus equivalentes en gRPC.

En la sección final del libro se examina cómo sacar el máximo partido de gRPC en la práctica. En esta sección se incluye información sobre el uso de herramientas adicionales, como contenedores de Docker o Kubernetes, para aprovechar la eficacia de gRPC. También se incluye una visión detallada de la supervisión con registro, métricas y seguimiento distribuido.

## <a name="who-this-guide-is-for"></a>Destinatarios de esta guía

Esta guía se ha escrito para desarrolladores que trabajan en .NET Framework o .NET Core que han usado WCF y que buscan migrar sus aplicaciones a un entorno de RPC moderno para .NET Core 3,0 y versiones posteriores. La guía también puede ser útil más en general para los desarrolladores que actualicen o consideren la posibilidad de actualizar a .NET y que quieran usar las herramientas de gRPC integradas.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](grpc-overview.md)

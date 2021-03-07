---
title: El mundo está distribuido.
description: Las ventajas y los desafíos de las aplicaciones distribuidas con un vistazo a los enfoques monolíticos y SOA.
author: robvet
ms.date: 02/07/2021
ms.openlocfilehash: b857355880c3942526d751312d98f2b822704759
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401833"
---
# <a name="the-world-is-distributed"></a>El mundo está distribuido.

Solo tiene que preguntar a los "niños fríos": *los sistemas modernos distribuidos se encuentran en y las aplicaciones monolíticas están fuera.*

Pero no solo se trata de "niños fríos". Los líderes de ti progresivos, los arquitectos corporativos y los desarrolladores de astutoss están devolviendo los mismos pensamientos que exploran y evalúan las aplicaciones distribuidas modernas. Muchos han comprado en. Están diseñando nuevas y replataformas aplicaciones empresariales existentes siguiendo los principios, patrones y prácticas de las aplicaciones de microservicios distribuidas.

Pero esta evolución plantea muchas preguntas...

- ¿Qué es exactamente una aplicación distribuida?
- ¿Por qué obtienen Popularidad?
- ¿Cuáles son los costos?
- Y, lo que es importante, ¿cuáles son los inconvenientes?

Para empezar, vamos a rebobinar y examinar los últimos 15 años. Durante este período, normalmente construimos aplicaciones como una sola unidad monolítica. En la figura 1-1 se muestra la arquitectura.

![Arquitectura monolítica.](./media/the-world-is-distributed/monolithic-design.png)

**Figura 1-1**. Arquitectura monolítica.

Observe cómo se ejecutan los módulos para pedidos, identidades y marketing en un proceso de servidor único. Los datos de la aplicación se almacenan en una base de datos compartida. La funcionalidad empresarial se expone a través de las interfaces HTML y RESTful.

En muchos sentidos, las aplicaciones monolíticas son `straightforward` . Son sencillos:

- Build
- Prueba
- Implementar
- Solución de problemas
- Escalar verticalmente (escalar verticalmente)

Sin embargo, las arquitecturas monolíticas pueden presentar desafíos importantes.

Con el tiempo, puede llegar a un punto en el que empiece a perder el control...

- El monolito ha dejado de ser tan complicado que nadie lo entienda.
- Usted teme realizar cambios, ya que cada uno lleva efectos secundarios imprevistos y costosos.
- Las nuevas características y correcciones se hacen más lentas y costosas de implementar.
- Incluso el cambio más pequeño requiere la implementación completa de toda la aplicación, costosa y arriesgada.
- Un componente inestable puede bloquear todo el sistema.
- Agregar nuevas tecnologías y marcos no es una opción.
- La implementación de metodologías de entrega ágil es difícil.
- La arquitectura de erosión se establece en a medida que la base de código se deteriora con "casos especiales".
- Finalmente, los asesores llegan y le indican que lo vuelva a escribir.

Los profesionales de ti llaman a esta condición `the Fear Cycle` . Si ha estado en el negocio de la tecnología durante cualquier período de tiempo, puede que lo haya experimentado. Está estresado y agota el presupuesto de ti. En lugar de crear soluciones nuevas e innovadoras, la mayor parte del presupuesto se dedica a mantener las aplicaciones heredadas.

En lugar de miedo, las empresas requieren `speed and agility` . Buscan un estilo arquitectónico con el que pueden responder rápidamente a las condiciones de mercado. Necesitan actualizar y escalar de forma instantánea áreas pequeñas de una aplicación activa.

Un intento temprano de obtener velocidad y agilidad llegó en forma de [arquitectura orientada a servicios](https://en.wikipedia.org/wiki/Service-oriented_architecture), o `SOA` . En este modelo, los consumidores de servicios y los proveedores de servicios se colaboran a través de componentes de mensajería de middleware, a menudo denominados [Service Bus empresariales](https://en.wikipedia.org/wiki/Enterprise_service_bus), o `ESB` . En la figura 1-2 se muestra la arquitectura.

![Oriente.](./media/the-world-is-distributed/soa-basic.png)

**Figura 1-2**. Arquitectura SOA.

Con SOA, proveedores de servicios centralizados registrados con ESB. La lógica de negocios se integrará en ESB para integrar proveedores y consumidores. Después, los consumidores del servicio pueden buscar y comunicarse con estos proveedores mediante ESB.

A pesar de las promesas de SOA, implementar este enfoque suele aumentar la complejidad y introducir cuellos de botella. Los costos de mantenimiento se hicieron altos y el middleware de ESB es costoso. Los servicios tienden a ser grandes. Suelen compartir las dependencias y el almacenamiento de datos. Al final, SOA a menudo dio como resultado una estructura "monolítica" distribuida con servicios centralizados que eran resistentes a los cambios.

En la actualidad, muchas organizaciones han logrado velocidad y agilidad mediante la adopción de un enfoque de arquitectura de microservicios distribuido para la creación de sistemas. En la figura 1-3 se muestra el mismo sistema creado mediante técnicas y prácticas distribuidas.

![Arquitectura distribuida.](./media/the-world-is-distributed/distributed-design.png)

**Figura 1-3**. Arquitectura distribuida.

Observe cómo se descompone la misma aplicación en un conjunto de servicios distribuidos. Cada es independiente y encapsula su propio código, datos y dependencias. Cada se implementa en un contenedor de software y se administra mediante un orquestador de contenedores. En lugar de una única base de datos compartida por varios servicios, cada servicio posee una base de datos privada. Otros servicios no pueden tener acceso a esta base de datos directamente y solo pueden acceder a los datos que se exponen a través de la API pública del servicio que la posee. Observe cómo algunos servicios requieren una base de datos relacional completa, pero otros, un almacén de datos NoSQL. El servicio de cesta almacena su estado en una caché de clave y valor distribuida. Observe cómo el tráfico entrante se enruta a través de un servicio de puerta de enlace de API. Es responsable de dirigir las llamadas a los servicios y aplicar las preocupaciones transversales. Lo más importante es que la aplicación aprovecha al máximo las características de escalabilidad, disponibilidad y resistencia que se encuentran en las plataformas en la nube modernas.

Sin embargo, aunque los servicios distribuidos pueden proporcionar agilidad y velocidad, presentan un conjunto diferente de desafíos. Tenga en cuenta lo siguiente...

- ¿Cómo pueden detectarse los servicios distribuidos entre sí y comunicarse sincrónicamente?
- ¿Cómo pueden implementar la mensajería asincrónica?
- ¿Cómo pueden mantener la información contextual en una transacción?
- ¿Cómo pueden ser resistentes a los errores?
- ¿Cómo se puede escalar para satisfacer la demanda fluctuante?
- ¿Cómo se supervisan y se observan?

Para cada uno de estos desafíos, a menudo hay varios productos disponibles. Sin embargo, el blindaje de la aplicación frente a las diferencias de producto y el mantenimiento del código y el portátil se convierten en un reto.

Este libro presenta DAPR. DAPR es un entorno de ejecución de aplicaciones distribuidas. Aborda directamente muchos de los desafíos que se encuentran junto con las aplicaciones distribuidas. En el futuro, DAPR tiene la posibilidad de tener un impacto profundo en el desarrollo de aplicaciones distribuidas.

## <a name="summary"></a>Resumen

En este capítulo, analizamos la adopción de aplicaciones distribuidas. Contrastamos un enfoque de sistema monolítico con el de los servicios distribuidos. Hemos señalado muchos de los desafíos comunes a la hora de considerar un enfoque distribuido.

Ahora, siéntese, relájese y permítanos introducir el nuevo mundo de DAPR.

>[!div class="step-by-step"]
>[Anterior](foreword.md)
>[Siguiente](dapr-at-20000-feet.md)

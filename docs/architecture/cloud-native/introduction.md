---
title: Introducción a las aplicaciones nativas en la nube
description: Más información sobre la informática nativa en la nube
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: e1f7683b6f3722bb91e611f199f2e9ce2bbefc63
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895522"
---
# <a name="introduction-to-cloud-native-applications"></a>Introducción a las aplicaciones nativas en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Otro día, en la oficina, trabajando en "el próximo panorama".

Sus anillos de teléfono móvil. Es el encargado de la contratación, que le llama dos veces al día sobre nuevos trabajos.

Pero esta vez es diferente: Inicio, equidad y mucho financiamiento.

La mención de la tecnología de la nube y la tecnología de vanguardia le inserciones en el perímetro.

Avance rápido unas cuantas semanas y ahora es un nuevo empleado en una sesión de diseño que diseña una importante aplicación de comercio electrónico. Va a competir con otros sitios de comercio electrónico líderes.

¿Cómo lo creará?

Si sigue las instrucciones de los últimos 15 años, lo más probable es que compile el sistema que se muestra en la figura 1,1.

![Diseño monolítico tradicional](./media/monolithic-design.png)

**Figura 1-1**. Diseño monolítico tradicional

Cree una aplicación de gran tamaño que contenga toda la lógica del dominio. Incluye módulos como identidad, catálogo, ordenación y mucho más. La aplicación principal se comunica con una base de datos relacional de gran tamaño. El núcleo expone la funcionalidad a través de una interfaz HTML.

¡Enhorabuena!  Acaba de crear una aplicación monolítica.

No todo está dañado. Los monolíticos ofrecen algunas ventajas distintas. Por ejemplo, son sencillos...

- build
- test
- implementar
- inalámbrica
- scale

Muchas aplicaciones correctas que existen hoy en día se crearon como monolíticos. La aplicación es un golpe y continúa evolucionando, iterando después de la iteración, agregando más funcionalidad.

Sin embargo, en algún momento se empieza a sentirse incómodo. Verá que pierde el control de la aplicación. A medida que pasa el tiempo, la sensación se vuelve más intensa y finalmente se especifica un estado conocido como el **ciclo de miedo**.

- La aplicación se ha convertido en una complicación abrumadora de que ninguna persona la entiende.
- Teme realizar cambios: cada cambio tiene efectos secundarios imprevistos y costosos.
- Las nuevas características y correcciones se vuelven difíciles de implementar y requieren mucho tiempo.
- Cada versión tan pequeña como puede ser requiere una implementación completa de toda la aplicación.
- Un componente inestable puede bloquear todo el sistema.
- Las nuevas tecnologías y marcos de trabajo no son una opción.
- Es difícil implementar metodologías de entrega ágiles.
- La arquitectura de erosión se establece en a medida que la base de código se deteriora con "casos especiales".
- Los asesores le indican que vuelva a escribirla.

Muchas organizaciones han abordado el ciclo de miedo monolítica mediante la adopción de un enfoque nativo de la nube para la creación de sistemas. En la figura 1-2 se muestra el mismo sistema creado para aplicar las técnicas y prácticas nativas en la nube.

![Diseño nativo en la nube](./media/cloud-native-design.png)

**Figura 1-2**. Diseño nativo en la nube

Observe cómo la aplicación se descompone en un conjunto de pequeños microservicios aislados. Cada servicio es independiente y encapsula su propio código, datos y dependencias. Cada se implementa en un contenedor de software y se administra mediante un orquestador de contenedores. En lugar de una base de datos relacional grande, cada servicio posee su propio almacén de datos, el tipo de que varía en función de las necesidades de datos. Tenga en cuenta que algunos servicios dependen de una base de datos relacional, pero otros en las bases de datos NoSQL. Un servicio almacena su estado en una caché distribuida. Tenga en cuenta cómo todo el tráfico se enruta a través de un servicio de puerta de enlace de API que es responsable de enrutar el tráfico a los servicios back-end principales y de aplicar muchas cuestiones transversales. Lo más importante es que la aplicación aprovecha al máximo las características de escalabilidad y resistencia que se encuentran en las plataformas en la nube modernas.

### <a name="cloud-native-computing"></a>Informática nativa en la nube

Hmm... Acabamos de usar el término "*Cloud Native*". En primer lugar, podría ser "lo que significa exactamente esto?". Otra moda del sector concocted por los proveedores de software para comercializar más cosas? "

Afortunadamente, es mucho diferente y, afortunadamente, este libro le ayudará a convencerle.

En poco tiempo, la nube nativa se ha convertido en una tendencia de conducción en el sector del software. Es una nueva manera de pensar en la creación de sistemas grandes y complejos, un enfoque que aprovecha al máximo las modernas prácticas de desarrollo de software, tecnologías e infraestructura en la nube. El enfoque cambia la manera de diseñar, implementar, implementar y poner en funcionamiento los sistemas.

A diferencia de la continuada que impulsa nuestro sector, la nube nativa es "*for-real*". Tenga en cuenta [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), un consorcio de más de 300 grandes corporaciones con un contrato para que la informática nativa en la nube sea omnipresente en las pilas de tecnología y en la nube. Como uno de los grupos de código abierto más influyentes, hospeda muchos de los proyectos de código abierto de más rápido crecimiento en GitHub. Incluyen proyectos como [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [envío](https://www.envoyproxy.io/)y [gRPC](https://grpc.io/).

El CNCF fomenta un ecosistema de código abierto y neutralidad entre proveedores. A continuación, presentamos principios, patrones y procedimientos recomendados nativos de la nube que son independientes de la tecnología. Al mismo tiempo, se describen los servicios y la infraestructura disponibles en la nube de Microsoft Azure para la creación de sistemas nativos en la nube.

Por lo tanto, ¿qué es la nube nativa? Siéntese, relájese y permítanos ayudarle a explorar este nuevo mundo.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](definition.md)

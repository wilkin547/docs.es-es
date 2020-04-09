---
title: Introducción a las aplicaciones nativas en la nube
description: Más información sobre la informática nativa de la nube
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: c9ffd34ec3deb04abddbbf85a9e5a6ed2b57c8f9
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989056"
---
# <a name="introduction-to-cloud-native-applications"></a>Introducción a las aplicaciones nativas en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Otro día, en la oficina, trabajando en "la próxima gran cosa".

Tu celular suena. Es tu amigable reclutador, el que te llama dos veces al día sobre nuevos trabajos.

Pero esta vez es diferente: Puesta en marcha, equidad y mucha financiación.

La mención de la nube y la tecnología de vanguardia te empuja al límite.

Avance rápido unas semanas y ahora eres un nuevo empleado en una sesión de diseño diseñando una aplicación de comercio electrónico importante. Te vas a completar con otros sitios de comercio electrónico líderes.

¿Cómo lo construirás?

Si sigue las instrucciones de los últimos 15 años, lo más probable es que compile el sistema que se muestra en la Figura 1.1.

![Diseño monolítico tradicional](./media/monolithic-design.png)

**Figura 1-1**. Diseño monolítico tradicional

Construir una aplicación principal de gran tamaño que contiene toda la lógica de dominio. Incluye módulos como Identidad, Catálogo, Pedidos y más. La aplicación principal se comunica con una base de datos relacional grande. El núcleo expone la funcionalidad a través de una interfaz HTML.

¡Enhorabuena!  Acaba de crear una aplicación monolítica.

No todo está mal. Los monolitos ofrecen algunas ventajas distintas. Por ejemplo, son fáciles de...

- build
- test
- implementar
- Solucionar problemas
- scale

Muchas aplicaciones exitosas que existen hoy en día se crearon como monolitos. La aplicación es un éxito y continúa evolucionando, iteración después de la iteración, añadiendo más y más funcionalidad.

En algún momento, sin embargo, usted comienza a sentirse incómodo. Usted se encuentra perdiendo el control de la aplicación. A medida que pasa el tiempo, la sensación se vuelve más intensa y finalmente entras en un estado conocido como el **Ciclo del Miedo.**

- La aplicación se ha vuelto tan abrumadoramente complicada que ninguna persona lo entiende.
- Temes hacer cambios - cada cambio tiene efectos secundarios involuntarios y costosos.
- Las nuevas características/correcciones se vuelven complicadas, lentas y costosas de implementar.
- Cada versión tan pequeña como sea requiere una implementación completa de toda la aplicación.
- Un componente inestable puede bloquear todo el sistema.
- Las nuevas tecnologías y marcos no son una opción.
- Es difícil implementar metodologías de entrega ágiles.
- La erosión arquitectónica se establece a medida que la base de código se deteriora con "casos especiales" interminables.
- Los consultores te dicen que lo vuelvas a escribir.

Muchas organizaciones han abordado el ciclo del miedo monolítico adoptando un enfoque nativo de la nube para construir sistemas. La Figura 1-2 muestra el mismo sistema creado aplicando técnicas y prácticas nativas de la nube.

![Diseño nativo de la nube](./media/cloud-native-design.png)

**Figura 1-2**. Diseño nativo de la nube

Observe cómo la aplicación se descompone en un conjunto de pequeños microservicios aislados. Cada servicio es independiente y encapsula su propio código, datos y dependencias. Cada uno se implementa en un contenedor de software y se administra mediante un orquestador de contenedores. En lugar de una base de datos relacional grande, cada servicio posee su propio almacén de datos, cuyo tipo varía en función de las necesidades de datos. Observe cómo algunos servicios dependen de una base de datos relacional, pero otros de bases de datos NoSQL. Un servicio almacena su estado en una memoria caché distribuida. Tenga en cuenta cómo todo el tráfico se enruta a través de un servicio de PUERTA de enlace de API que es responsable de enrutar el tráfico a los servicios back-end principales y de aplicar muchas preocupaciones transversales. Lo más importante es que la aplicación aprovecha al máximo las características de escalabilidad y resistencia que se encuentran en las plataformas en la nube modernas.

### <a name="cloud-native-computing"></a>Computación nativa de la nube

Hmm... Acabamos de usar el término "*Cloud Native*." Primero pensaste que podría ser, "¿Qué significa eso exactamente?" Otra palabra de moda de la industria inventada por los proveedores de software para comercializar más cosas?

Afortunadamente es muy diferente y espero que este libro te ayude a convencerte.

En poco tiempo, la nube nativa se ha convertido en una tendencia impulsora en la industria del software. Es una nueva forma de pensar en la creación de sistemas grandes y complejos, un enfoque que aprovecha al máximo las prácticas modernas de desarrollo de software, las tecnologías y la infraestructura en la nube. El enfoque cambia la forma en que diseña, implementa, implementa y opera los sistemas.

A diferencia del bombo continuo que impulsa nuestra industria, nativo de la nube es *"real".* Consideremos [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), un consorcio de más de 300 grandes corporaciones con una carta para hacer que la computación nativa de la nube sea omnipresente en la tecnología y las pilas en la nube. Como uno de los grupos de código abierto más influyentes, alberga muchos de los proyectos de código abierto de más rápido crecimiento en GitHub. Incluyen proyectos como [Kubernetes,](https://kubernetes.io/) [Prometheus,](https://prometheus.io/) [Helm,](https://helm.sh/) [Envoy](https://www.envoyproxy.io/)y [gRPC.](https://grpc.io/)

El CNCF fomenta un ecosistema de código abierto y neutralidad de proveedores. Siguiendo con ese ejemplo, presentamos principios nativos de la nube, patrones y prácticas recomendadas que son agnósticos de la tecnología. Al mismo tiempo, analizamos los servicios y la infraestructura disponibles en la nube de Microsoft Azure para la construcción de sistemas nativos de la nube.

Entonces, ¿qué es exactamente Cloud Native? Siéntate, relájate y ayúdanos a explorar este nuevo mundo.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](definition.md)

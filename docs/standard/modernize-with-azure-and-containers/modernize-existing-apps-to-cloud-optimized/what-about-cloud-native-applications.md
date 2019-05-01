---
title: ¿Qué son las aplicaciones nativas para la nube?
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | ¿Qué sucede con las aplicaciones nativas de la nube?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 10f7761b7c0d2ddd8cb9247b1a02aa49cdc4e5d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012131"
---
# <a name="what-about-cloud-native-applications"></a>¿Qué son las aplicaciones nativas para la nube?

Aunque [nativas de la nube](https://azure.microsoft.com/overview/cloudnative/) las aplicaciones no son el enfoque principal de esta guía, es útil para obtener una descripción de este nivel de madurez de modernización y para distinguirlas de las aplicaciones optimizadas para la nube.

Figura 4-3 coloca las aplicaciones nativas de nube en los niveles de madurez de modernización de aplicaciones:

![Colocación de aplicaciones nativas de nube](./media/image3.png)

> **Figura 4-3.** Colocación de aplicaciones nativas de nube

Normalmente, el nivel de madurez de modernización nativas de la nube requiere nuevas inversiones de desarrollo. Pasar al nivel nativo en la nube generalmente está controlado por la necesidad empresarial para modernizar aplicaciones tanto como sea posibles mejorar drásticamente la escalabilidad en aplicaciones de gran tamaño mediante la creación de subsistemas autónomos (microservicios) que se pueden implementar y escalar por separado en otras áreas de la aplicación mientras reduce los costes en la agilidad de evolución largo plazo y aumento de partes de la aplicación de esos autónomos que proporcionan importantes compiten ventajas.

Los principales pilares de las aplicaciones nativas de la nube se basan en enfoques de arquitectura de microservicios, que pueden evolucionar con agilidad y escale a los límites que serían difíciles de lograr en una arquitectura monolítica, implementada en un entorno local o en la nube entorno.

Figura 4-4 muestra las principales características del modelo nativas de la nube.

> ![Las características nativas de la nube son los Microservicios, los orquestadores de contenedores, en la nube resistentes y sin servidor](./media/image4.png)
>
> **Figura 4-4.** Características nativas de la nube

Además, puede ampliar las aplicaciones web modernas básica y las aplicaciones nativas de nube mediante la adición de otros servicios, como IoT, aprendizaje automático (ML) y la inteligencia artificial (AI). Puede usar cualquiera de estos servicios para ampliar cualquiera de los posibles enfoques optimizada para la nube.

La diferencia fundamental en las aplicaciones en el nivel nativo en la nube está en la arquitectura de aplicación. Aplicaciones nativas de nube son, por definición, las aplicaciones basadas en microservicios. Las aplicaciones nativas de nube requieren arquitecturas especiales, tecnologías y plataformas, en comparación con una aplicación monolítica web o aplicación tradicional de N niveles.

## <a name="cloud-native-applications-details"></a>Detalles de aplicaciones nativas de nube

Nativo en la nube es un estado más avanzado o para adultos para aplicaciones de gran tamaño y de misión crítica. Las aplicaciones nativas de la nube suelen requieran la arquitectura y diseño que se crean desde cero en lugar de mediante la modernización de las aplicaciones existentes. La diferencia clave entre una aplicación nativa de la nube y una aplicación web optimizada para la nube más sencilla es la recomendación de usar arquitecturas de microservicios en un enfoque nativas de la nube. También pueden ser aplicaciones optimizadas para la nube aplicaciones web monolíticas o aplicaciones de N niveles.

El [aplicación Twelve-Factor](https://12factor.net/) (una colección de modelos que están estrechamente relacionados con los enfoques de microservicios) también se considera un requisito para las arquitecturas de aplicaciones nativas de la nube.

El [Foundation de informática nativo en la nube (CNCF)](https://www.cncf.io/) es un promotor de principios nativas de la nube principal. Microsoft es un [miembro de la CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Para obtener una definición de ejemplo y para obtener más información sobre las características de aplicaciones nativas de nube, consulte el artículo de Gartner [cómo construir y diseñar aplicaciones nativas de nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Para obtener instrucciones específicas de Microsoft sobre cómo implementar una aplicación nativa de la nube, consulte [microservicios de. NET: Arquitectura para aplicaciones .NET en contenedor](https://aka.ms/microservicesebook).

El factor más importante a tener en cuenta si migra una aplicación completa para el modelo de nube nativas es que debe rediseñar a una arquitectura basada en microservicios. Claramente, esto requiere una inversión importante en el desarrollo debido al proceso de refactorización grande implicado. Normalmente, se elige esta opción para aplicaciones críticas que necesitan nuevos niveles de escalabilidad y agilidad a largo plazo. Sin embargo, puede empezar la creciente nativas de la nube mediante la adición de microservicios para pocos escenarios nuevos y finalmente refactorizar la aplicación por completo como microservicios. Se trata de un enfoque incremental que es la mejor opción para algunos escenarios.

## <a name="what-about-microservices"></a>¿Qué microservicios?

Es importante entender los microservicios y cómo funcionan, cuando se piensa en aplicaciones nativas de nube para su organización.

La arquitectura de microservicios es un enfoque avanzado que puede usar para las aplicaciones que se crean desde el principio o al desarrollar las aplicaciones existentes a aplicaciones nativas de la nube. Puede iniciar mediante la adición de algunos microservicios para las aplicaciones existentes para obtener información sobre los nuevos paradigmas de microservicios. Pero evidentemente, deberá arquitecto y el código, especialmente para este tipo de enfoque de arquitectura.

Sin embargo, microservicios no son obligatorios para cualquier aplicación moderna o nuevo. Microservicios no están "mágica" y no son la mejor, solo puede crear todas las aplicaciones. Cómo y cuándo usar microservicios depende del tipo de aplicación que necesita para compilar.

La arquitectura de microservicios se está convirtiendo en el método preferido para aplicaciones críticas distribuidas y grandes o complejas que se basan en múltiples subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicios, una aplicación se compila como una colección de servicios que puede ser desarrollados de forma independiente, probar, versionear, implementar y escalar. Esto puede incluir cualquier base de datos autónomo, relacionado por microservicio.

Para una visión detallada de una arquitectura de microservicios que se puede implementar mediante el uso de .NET Core, consulte el PDF libro electrónico descargable [microservicios de. NET: Arquitectura para aplicaciones .NET en contenedor](https://aka.ms/microservicesebook). La guía también está disponible [online](../../microservices-architecture/index.md).

Pero incluso en escenarios en los que los microservicios ofrecen la implementación eficaz de capacidades independientes, los límites de subsistema seguros y diversidad de tecnología-también suponen muchos nuevos desafíos. Los desafíos relacionados con el desarrollo de aplicaciones distribuidas, como modelos de datos fragmentados e independientes. para lograr una comunicación resistente entre microservicios; la necesidad de la coherencia eventual; y la complejidad operativa. Microservicios presentan un mayor nivel de complejidad en comparación con las aplicaciones tradicionales monolíticas.

Dada la complejidad de una arquitectura de microservicios, solo escenarios específicos y determinados tipos de aplicación son adecuados para las aplicaciones basadas en microservicio. Estos incluyen aplicaciones grandes y complejas que tienen varias evolucionando subsistemas. En estos casos, resulta que vale la pena invertir en una arquitectura de software más compleja, para una mayor agilidad a largo plazo y el mantenimiento de aplicación más eficaz. Pero para escenarios menos complejos, podría ser mejor continuar con un enfoque de la aplicación monolítica o se aproxima más sencilla de N niveles.

Como una nota final, incluso con el riesgo de ser repetitiva acerca este concepto, no debería intentar usar microservicios en las aplicaciones como "todo o nada en absoluto". Puede ampliar y desarrollar las aplicaciones monolíticas existentes agregando nuevos, pequeños escenarios basados en microservicios. No es necesario empezar desde cero para empezar a trabajar con un enfoque de arquitectura de microservicios. De hecho, se recomienda que desarrollan del uso de una aplicación de N niveles o monolítica existente mediante la adición de nuevos escenarios. Finalmente, puede dividir la aplicación en componentes autónomos o microservicios. Puede empezar a desarrollar sus aplicaciones monolíticas en una dirección de microservicios, paso a paso.

En cualquier caso, el resto de esta guía centra principalmente en "ninguna aplicación basada en microservicios" porque esta guía está destinada principalmente la modernización de las aplicaciones existentes que suelen tener arquitecturas de N niveles o monolíticas.

> [!div class="step-by-step"]
> [Anterior](microsoft-technologies-in-cloud-optimized-applications.md)
> [Siguiente](deploy-existing-net-apps-as-windows-containers.md)

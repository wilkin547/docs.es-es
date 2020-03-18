---
title: ¿Qué son las aplicaciones nativas para la nube?
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | ¿Qué ocurre con las aplicaciones nativas de la nube?
ms.date: 04/28/2018
ms.openlocfilehash: d2a7f89e347d75ddbdae84c8eb57e32447b83297
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543552"
---
# <a name="what-about-cloud-native-applications"></a>¿Qué son las aplicaciones nativas para la nube?

Aunque las aplicaciones [nativas de la nube](https://azure.microsoft.com/overview/cloudnative/) no son el objetivo principal de esta guía, es útil conocer este nivel de madurez de modernización y distinguirlas de las aplicaciones optimizadas para la nube.

La figura 4-3 coloca las aplicaciones nativas de la nube en los niveles de madurez de modernización de las aplicaciones:

![Diagrama que muestra cómo colocar las aplicaciones nativas de la nube.](./media/what-about-cloud-native-applications/positioning-cloud-native-applications.png)

**Figura 4-3.** Posicionamiento de las aplicaciones nativas de la nube

Normalmente, el nivel de madurez de modernización "nativo de la nube" requiere nuevas inversiones de desarrollo. El traslado al nivel nativo de la nube normalmente se basa en la necesidad empresarial de modernizar las aplicaciones tanto como sea posible para mejorar notablemente la escala de las aplicaciones de gran tamaño mediante la creación de subsistemas autónomos (microservicios) que se pueden implementar y escalar de forma independiente de otras áreas de la aplicación, a la vez que se reducen los costos a largo plazo y se aumenta la agilidad de la evolución de esas partes de la aplicación autónoma que proporcionan importantes ventajas en términos de competitividad.

Los principales pilares de las aplicaciones nativas de la nube se basan en enfoques de arquitectura de microservicios, que pueden evolucionar con agilidad y escalar a límites que serían difíciles de lograr con una arquitectura monolítica, implementada en el entorno local o en la nube.

En la figura 4-4 se muestran las principales características del modelo nativo de la nube.

![Diagrama que muestra las principales características del modelo nativo de la nube.](./media/what-about-cloud-native-applications/cloud-native-characteristics.png)

**Figura 4-4.** Características del modelo nativo de la nube

Además, puede ampliar las modernas aplicaciones web básicas y las aplicaciones nativas de la nube agregando otros servicios, como inteligencia artificial, aprendizaje automático e IoT. Puede usar cualquiera de estos servicios para ampliar cualquiera de los posibles enfoques optimizados para la nube.

La diferencia fundamental en las aplicaciones en el nivel nativo de la nube está en la arquitectura de la aplicación. Las aplicaciones nativas de la nube son, por definición, aplicaciones basadas en microservicios. Las aplicaciones nativas de la nube requieren arquitecturas, tecnologías y plataformas especiales, en comparación con una aplicación web monolítica o una aplicación tradicional de N niveles.

## <a name="cloud-native-applications-details"></a>Detalles sobre las aplicaciones nativas de la nube

Nativo de la nube es un estado más avanzado o maduro para aplicaciones grandes y críticas. Las aplicaciones nativas de la nube suelen requerir una arquitectura y un diseño que se crean desde cero en lugar de modernizar las aplicaciones existentes. La principal diferencia entre una aplicación nativa de la nube y una aplicación web más sencilla optimizada para la nube es la recomendación de usar arquitecturas de microservicios en el enfoque nativo de la nube. Las aplicaciones optimizadas para la nube también pueden ser aplicaciones web monolíticas o aplicaciones de N niveles.

La [aplicación de doce factores](https://12factor.net/) (una colección de patrones que están estrechamente relacionados con los enfoques de microservicios) también se considera un requisito para la arquitectura de las aplicaciones nativas de la nube.

[Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) es un importante promotor de principios del modelo nativo de la nube. Microsoft es [miembro de CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Para obtener instrucciones detalladas sobre cómo diseñar y desarrollar aplicaciones nativas en la nube, lea los siguientes libros electrónicos gratuitos:

* [Diseño de aplicaciones de .NET nativas en la nube para Azure](../../cloud-native/introduction.md)
* [Microservicios de .NET. Arquitectura para aplicaciones .NET en contenedor](../../microservices/index.md).

El factor más importante que hay que tener en cuenta si migra una aplicación completa al modelo nativo de la nube es que debe rediseñar una arquitectura basada en microservicios. Esto requiere claramente una inversión significativa en desarrollo debido al gran proceso de refactorización que implica. Esta opción se elige normalmente para las aplicaciones críticas que necesitan nuevos niveles de escalabilidad y agilidad a largo plazo. Sin embargo, puede empezar el traslado al modelo nativo de la nube agregando microservicios para unos pocos escenarios nuevos y, finalmente, refactorizar la aplicación por completo como microservicios. Este es un enfoque incremental que es la mejor opción para algunos escenarios.

## <a name="what-about-microservices"></a>¿Qué hay de los microservicios?

Comprender los microservicios y cómo funcionan es importante si está pensando en aplicaciones nativas de la nube para su organización.

La arquitectura de microservicios es un enfoque avanzado que puede usar para aplicaciones creadas desde cero o cuando evolucione las aplicaciones existentes hacia aplicaciones nativas de la nube. Puede empezar agregando algunos microservicios a las aplicaciones existentes para aprender los nuevos paradigmas de los microservicios. Pero claramente, necesita diseñar y programar, especialmente en este tipo de enfoque arquitectónico.

Sin embargo, los microservicios no son obligatorios para una aplicación nueva o moderna. Los microservicios no son mágicos y no son la mejor manera de crear todas las aplicaciones. Cómo y cuándo se usan los microservicios depende del tipo de aplicación que se debe crear.

La arquitectura de microservicios se está convirtiendo en el método preferido para aplicaciones críticas distribuidas y grandes o complejas basadas en múltiples subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicios, una aplicación se crea como una colección de servicios que se pueden desarrollar, probar, implementar y escalar de forma independiente, y crear versiones de ella. Esto puede incluir cualquier base de datos autónoma relacionada por microservicio.

Para ver información detallada de una arquitectura de microservicios que puede implementar con .NET Core, consulte el libro electrónico en PDF descargable [Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor](https://aka.ms/microservicesebook). La guía también está disponible [en línea](../../microservices/index.md).

Sin embargo, incluso en escenarios en los que los microservicios ofrecen una implementación eficaz e independiente de la funcionalidad, límites de subsistema seguros y diversidad tecnológica, también plantean muchos desafíos nuevos. Los desafíos son, entre otros: el desarrollo de aplicaciones distribuidas, como los modelos de datos fragmentados e independientes; lograr una comunicación resistente entre los microservicios; la necesidad de coherencia final; y la complejidad operativa. Los microservicios presentan un nivel de complejidad mayor en comparación con las aplicaciones monolíticas tradicionales.

Debido a la complejidad de la arquitectura de microservicios, solo algunos escenarios específicos y determinados tipos de aplicaciones son adecuados para las aplicaciones basadas en microservicios. Entre ellas se incluyen las aplicaciones grandes y complejas que tienen varios subsistemas en evolución. En estos casos, merece la pena invertir en una arquitectura de software más compleja para aumentar la agilidad a largo plazo y la eficacia del mantenimiento de las aplicaciones. Pero en escenarios menos complejos, podría ser mejor continuar con un enfoque de aplicación monolítica o enfoques de N niveles más sencillos.

Como nota final, y a riesgo de ser repetitivos sobre este concepto, no considere el uso de microservicios en las aplicaciones como "todo o nada". Puede extender y desarrollar las aplicaciones monolíticas existentes agregando nuevos escenarios pequeños basados en microservicios. No es necesario empezar desde cero para empezar a trabajar con un enfoque de arquitectura de microservicios. De hecho, se recomienda que parta de una aplicación monolítica o de N niveles existente y le agregue nuevos escenarios. Finalmente, puede dividir la aplicación en componentes o microservicios autónomos. Puede empezar a desarrollar aplicaciones monolíticas pensando en los microservicios, paso a paso.

En cualquier caso, el resto de esta guía se centra principalmente en los casos en los que no hay aplicaciones basadas en microservicios, ya que esta guía está pensada para modernizar las aplicaciones existentes que normalmente tienen arquitecturas monolíticas o de N niveles.

> [!div class="step-by-step"]
> [Anterior](microsoft-technologies-in-cloud-optimized-applications.md)
> [Siguiente](deploy-existing-net-apps-as-windows-containers.md)

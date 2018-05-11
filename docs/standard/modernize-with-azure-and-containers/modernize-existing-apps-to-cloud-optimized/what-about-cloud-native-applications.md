---
title: ¿Qué sucede con las aplicaciones nativas de la nube?
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | ¿Qué sucede con las aplicaciones nativas de la nube?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 0e880689001ece2b770811cfbe3fea43aa425b32
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="what-about-cloud-native-applications"></a>¿Qué sucede con las aplicaciones nativas de la nube?

Aunque [nativo en la nube](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) aplicaciones no son el objetivo principal de esta guía, resulta útil para obtener una descripción de este nivel de madurez modernización y para distinguirlo de aplicaciones optimizada para la nube.

Figura 4-3 coloca aplicaciones de nube nativo en los niveles de madurez de modernización de aplicación:

![Posición de las aplicaciones de nube nativo](./media/image3.png)

> **Figura 4-3.** Posición de las aplicaciones de nube nativo

El nivel de madurez de modernización nativo en la nube normalmente requiere nuevas inversiones de desarrollo. Mover al nivel nativo en la nube normalmente está controlada por la necesidad empresarial de modernizar las aplicaciones tanto como sea posibles mejorar drásticamente la escala en aplicaciones de gran tamaño mediante la creación de subsistemas autónomos (microservicios) que se pueden implementar y la escala por separado de otras áreas de la aplicación mientras reduce los costos de la agilidad de la evolución de término y aumento largo de partes de la aplicación de esos autónomos que proporcionan importantes compiten ventajas. 

Los principales pilares de [nativo en la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) aplicaciones se basan en enfoques de arquitectura de microservicios, que pueden evolucionar con agilidad y escalar límites que serían difíciles de lograr en una arquitectura monolítica implementada como entorno de nube o local.

Figura 4-4 muestra las principales características del modelo de nube nativo.  

> ![Características de nube nativo son Microservicios, contenedores, en la nube resistentes, orchestrators y serverles](./media/image4.png)
>
> **Figura 4-4.** Características de nube nativo

Además, puede ampliar aplicaciones web modernos básica y las aplicaciones de nube nativo mediante la adición de otros servicios, como inteligencia artificial (AI), el aprendizaje automático (ML) e IoT. Puede usar cualquiera de estos servicios para extender cualquiera de los posibles enfoques optimizada para la nube.

La diferencia fundamental en las aplicaciones en el nivel nativo en la nube está en la arquitectura de la aplicación. [En la nube nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) aplicaciones son, por definición, las aplicaciones que se basan en microservicios. Las aplicaciones de nube nativo requieren arquitecturas especial, las tecnologías y plataformas, en comparación con una aplicación web monolítico o aplicación tradicional de N niveles.

## <a name="cloud-native-applications-details"></a>Detalles de las aplicaciones de nube nativo

[En la nube nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) es un estado más avanzado o consolidado para aplicaciones de gran tamaño y de misión crítica. Las aplicaciones de nube nativo suelen requieran la arquitectura y el diseño que se crean desde el principio en lugar de por modernizar las aplicaciones existentes. La diferencia clave entre una aplicación nativa en la nube y una aplicación web optimizada para la nube más sencilla es la recomendación para usar microservicios arquitecturas en un enfoque de nativo en la nube. También pueden ser aplicaciones optimizada para la nube aplicaciones web monolítico o aplicaciones con N niveles.

El [aplicación de Factor de doce](https://12factor.net/) (una colección de modelos que están estrechamente relacionados a los enfoques microservicios) también se considera un requisito para [nativo en la nube](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) arquitecturas de aplicación.

El [Foundation de informática nativo de nube (CNCF)](https://www.cncf.io/) está activa un promotor principal de principios de nativo en la nube. Microsoft es un [miembro de la CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Para obtener una definición de ejemplo y para obtener más información acerca de las características de aplicaciones de nube nativo, vea el artículo de Gartner [cómo diseñar la arquitectura y las aplicaciones de nube nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Para obtener instrucciones específicas de Microsoft acerca de cómo implementar una aplicación nativa en la nube, consulte [microservicios. NET: arquitectura de aplicaciones .NET en contenedores](https://aka.ms/microservicesebook).

El factor más importante a tener en cuenta si migra una aplicación completa para el [nativo en la nube](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) modelo es que debe cambie la arquitectura para una arquitectura basada en microservicios. Claramente Esto requiere una inversión importante en el desarrollo como consecuencia del proceso de refactorización grande implicado. Normalmente, se elige esta opción para aplicaciones de misión crítica que necesitan nuevos niveles de escalabilidad y la agilidad a largo plazo. Pero, puede comenzar a mover hacia la nube nativo mediante la adición de microservicios para unos pocos escenarios nuevos y finalmente refactorizar la aplicación completamente como microservicios. Se trata de un enfoque incremental que es la mejor opción para algunos escenarios.

## <a name="what-about-microservices"></a>¿Qué ocurre con microservicios? 

Cuando está pensando en las aplicaciones de nube nativo para su organización, es importante entender microservicios y cómo funcionan.

La arquitectura de microservicios es un enfoque avanzado que puede usar para las aplicaciones que se crean desde el principio o al desarrollar las aplicaciones existentes a las aplicaciones de nube nativo. Puede empezar agregando unos microservicios en las aplicaciones existentes para obtener información sobre los nuevos paradigmas de microservicios. Pero claramente, necesitará arquitecto y el código, especialmente para este tipo de enfoque de arquitectura.

Sin embargo, no son obligatorios para cualquier aplicación nueva o moderna microservicios. Microservicios no son "mágica", y no son la forma única y recomendada para crear todas las aplicaciones. Cómo y cuándo usar microservicios depende del tipo de aplicación que necesita para compilar.

La arquitectura de microservicios se está convirtiendo en el método preferido para aplicaciones de misión crítica distribuidas y grandes o complejas que se basan en varios subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicios, una aplicación se compila como una colección de servicios que pueden ser independientemente desarrollado, probado, control de versiones, implementar y escalar. Esto puede incluir cualquier base de datos relacionada, autónomo por microservicio.

Para obtener una visión detallada de una arquitectura de microservicios se puede implementar mediante .NET Core, vea el PDF libro electrónico descargable [microservicios. NET: arquitectura de aplicaciones .NET en contenedores](https://aka.ms/microservicesebook). La guía también está disponible [en línea](../../microservices-architecture/index.md).

Pero incluso en escenarios en que microservicios ofrecen eficaz de independiente de las capacidades de implementación y los límites de subsistema seguro, diversidad de tecnología-también activan muchos desafíos nuevos. Los desafíos relacionados con el desarrollo de aplicaciones distribuidas, como los modelos de datos fragmentados y es independiente; para lograr una comunicación resistente entre microservicios; la necesidad de coherencia definitiva; y la complejidad operativa. Microservicios presentan un mayor nivel de complejidad en comparación con las aplicaciones tradicionales monolíticas.

Dada la complejidad de una arquitectura de microservicios, sólo ciertos tipos de aplicaciones y escenarios específicos son adecuados para aplicaciones basadas en microservicio. Estas soluciones incluyen aplicaciones grandes y complejas que tienen varios evolucionando subsistemas. En estos casos, merece la pena invertir en una arquitectura de software más compleja, para una mayor agilidad a largo plazo y el mantenimiento de aplicación más eficaz. Pero para escenarios menos complejos, podría ser mejor continuar con un enfoque de aplicación monolítico o acerca de N niveles más sencilla.

Como una nota final, incluso con el riesgo de que es repetitivos sobre este concepto, no debe intentar usar microservicios en las aplicaciones como "todo o nada en absoluto". Puede extender y desarrollar aplicaciones monolíticas existentes agregando nuevos, pequeños escenarios basados en microservicios. No es necesario empezar desde cero para empezar a trabajar con un enfoque de arquitectura de microservicios. De hecho, se recomienda que los evolucionar del uso de una aplicación existente de monolítica o N niveles mediante la adición de nuevos escenarios. Finalmente, puede dividir la aplicación en componentes autónomos o microservicios. Puede iniciar la evolución de las aplicaciones monolíticas en una dirección de microservicios, paso a paso.

En cualquier caso, el resto de esta guía está presente centra principalmente en "ninguna aplicación basada en microservicios" porque esta guía está destinada principalmente la modernización de las aplicaciones existentes que normalmente tienen arquitecturas monolíticas o con N niveles.


>[!div class="step-by-step"]
[Anterior](microsoft-technologies-in-cloud-optimized-applications.md)
[Siguiente](deploy-existing-net-apps-as-windows-containers.md)

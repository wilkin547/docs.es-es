---
title: ¿Qué son las aplicaciones nativas para la nube?
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | ¿Qué ocurre con las aplicaciones nativas de la nube?
ms.date: 04/28/2018
ms.openlocfilehash: 26adb87c426442ebf0e88165e521819e3a49d175
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578018"
---
# <a name="what-about-cloud-native-applications"></a>¿Qué son las aplicaciones nativas para la nube?

Aunque las aplicaciones nativas de [la nube](https://azure.microsoft.com/overview/cloudnative/) no son el objetivo principal de esta guía, es útil conocer este nivel de madurez de modernización y distinguirlo de las aplicaciones optimizadas para la nube.

La figura 4-3 coloca las aplicaciones nativas en la nube en los niveles de madurez de modernización de aplicaciones:

![Posicionamiento de aplicaciones nativas en la nube](./media/image3.png)

> **Figura 4-3.** Posicionamiento de aplicaciones nativas en la nube

Normalmente, el nivel de madurez de modernización nativo de la nube requiere nuevas inversiones de desarrollo. Pasar al nivel nativo de la nube se basa normalmente en la necesidad empresarial de modernizar las aplicaciones tanto como sea posible para mejorar drásticamente la escala en aplicaciones de gran tamaño mediante la creación de subsistemas autónomos (microservicios) que se pueden implementar y escalar de forma independiente. desde otras áreas de la aplicación, a la vez que reduce los costos a largo plazo y aumenta la agilidad de la evolución de esas partes de la aplicación autónoma que proporcionan ventajas de competir significativas.

Los principales pilares de las aplicaciones nativas en la nube se basan en los enfoques de arquitectura de microservicios, que pueden evolucionar con agilidad y escalar a los límites que serían difíciles de lograr en una arquitectura monolítica, implementada en el entorno local o en la nube. entorno.

En la figura 4-4 se muestran las principales características del modelo nativo de la nube.

> ![Las características nativas en la nube son microservicios, contenedores, resistentes en la nube, orquestadores y sin servidor](./media/image4.png)
>
> **Figura 4-4.** Características nativas de la nube

Además, puede ampliar aplicaciones web modernas básicas y aplicaciones nativas en la nube agregando otros servicios, como inteligencia artificial (AI), machine learning (ML) y IoT. Puede usar cualquiera de estos servicios para extender cualquiera de los posibles enfoques optimizados para la nube.

La diferencia fundamental en las aplicaciones en el nivel nativo de la nube está en la arquitectura de la aplicación. Las aplicaciones nativas en la nube son, por definición, aplicaciones basadas en microservicios. Las aplicaciones nativas en la nube requieren arquitecturas, tecnologías y plataformas especiales, en comparación con una aplicación web monolítica o una aplicación tradicional de N niveles.

## <a name="cloud-native-applications-details"></a>Detalles de aplicaciones nativas de la nube

La nube nativa es un estado más avanzado o maduro para aplicaciones grandes y críticas. Las aplicaciones nativas de la nube suelen requerir arquitectura y diseño que se crean desde cero en lugar de modernizar las aplicaciones existentes. La principal diferencia entre una aplicación nativa en la nube y una aplicación Web más sencilla optimizada para la nube es la recomendación de usar arquitecturas de microservicios en un enfoque nativo de la nube. Las aplicaciones optimizadas para la nube también pueden ser aplicaciones web monolíticas o aplicaciones de N niveles.

La [aplicación de doce factores](https://12factor.net/) (una colección de patrones que están estrechamente relacionados con los enfoques de microservicios) también se considera un requisito para las arquitecturas de aplicaciones nativas de la nube.

[Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) es un promotor principal de principios nativos de la nube. Microsoft es [miembro de CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Para ver una definición de ejemplo y obtener más información sobre las características de las aplicaciones nativas de la nube, consulte el artículo de Gartner [Cómo diseñar y diseñar aplicaciones nativas](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)en la nube. Para obtener instrucciones específicas de Microsoft sobre cómo implementar una aplicación nativa en la nube, [consulte microservicios de .net: Arquitectura de aplicaciones](https://aka.ms/microservicesebook).net en contenedor.

El factor más importante a tener en cuenta si migra una aplicación completa al modelo nativo de la nube es que debe rediseñar una arquitectura basada en microservicios. Esto requiere claramente una inversión significativa en el desarrollo debido al gran proceso de refactorización implicado. Esta opción se elige normalmente para las aplicaciones críticas que necesitan nuevos niveles de escalabilidad y agilidad a largo plazo. Sin embargo, puede empezar a pasar a la plataforma nativa mediante la adición de microservicios para unos pocos escenarios nuevos y, finalmente, refactorizar la aplicación por completo como microservicios. Se trata de un enfoque incremental que es la mejor opción para algunos escenarios.

## <a name="what-about-microservices"></a>¿Qué ocurre con los microservicios?

Comprender los microservicios y cómo funcionan es importante cuando está pensando en aplicaciones nativas de la nube para su organización.

La arquitectura de microservicios es un enfoque avanzado que puede usar para aplicaciones creadas desde cero o cuando evolucione aplicaciones existentes hacia aplicaciones nativas en la nube. Puede empezar agregando algunos microservicios a las aplicaciones existentes para obtener información sobre los nuevos paradigmas de microservicios. Pero claramente, necesita diseñar y programar, especialmente para este tipo de enfoque arquitectónico.

Sin embargo, los microservicios no son obligatorios para una aplicación nueva o moderna. Los microservicios no son una "viñeta mágica" y no son la mejor manera de crear cada aplicación. Cómo y cuándo se usan los microservicios depende del tipo de aplicación que se debe compilar.

La arquitectura de microservicios se está convirtiendo en el método preferido para aplicaciones críticas distribuidas y grandes o complejas basadas en varios subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicios, una aplicación se crea como una colección de servicios que se pueden desarrollar, probar, crear versiones, implementar y escalar de forma independiente. Esto puede incluir cualquier base de datos autónoma relacionada por microservicio.

Para obtener una visión detallada de una arquitectura de microservicios que puede implementar con .net Core, consulte los microservicios de .net de [libro electrónico descargable PDF: Arquitectura de aplicaciones](https://aka.ms/microservicesebook).net en contenedor. La guía también está disponible [en línea](../../microservices/index.md).

Sin embargo, incluso en escenarios en los que los microservicios ofrecen una implementación independiente de funcionalidades, límites de subsistema seguro y diversidad tecnológica, también plantean muchos desafíos nuevos. Los desafíos están relacionados con el desarrollo de aplicaciones distribuidas, como los modelos de datos fragmentados e independientes. lograr una comunicación resistente entre los microservicios; la necesidad de coherencia final; y la complejidad operativa. Los microservicios presentan un nivel de complejidad superior en comparación con las aplicaciones monolíticas tradicionales.

Debido a la complejidad de una arquitectura de microservicios, solo los escenarios específicos y determinados tipos de aplicaciones son adecuados para las aplicaciones basadas en microservicios. Entre ellas se incluyen aplicaciones grandes y complejas que tienen varios subsistemas en evolución. En estos casos, merece la pena invertir en una arquitectura de software más compleja, para aumentar la agilidad a largo plazo y el mantenimiento de aplicaciones más eficaz. Pero para escenarios menos complejos, podría ser mejor continuar con un enfoque de aplicación monolítica o enfoques de N niveles más sencillos.

Como nota final, incluso en el riesgo de ser repetitivos sobre este concepto, no debería considerar el uso de microservicios en las aplicaciones como "todo en nada". Puede extender y desarrollar aplicaciones monolíticas existentes agregando nuevos escenarios pequeños basados en microservicios. No es necesario empezar desde cero para empezar a trabajar con un enfoque de arquitectura de microservicios. De hecho, se recomienda que evolucione del uso de una aplicación monolítica o de N niveles existente agregando nuevos escenarios. Finalmente, puede dividir la aplicación en componentes o microservicios autónomos. Puede empezar a desarrollar aplicaciones monolíticas en una dirección de microservicios, paso a paso.

En cualquier caso, el resto de esta guía está presente en la mayoría de los casos en "no hay aplicaciones basadas en microservicios", ya que esta guía está dirigida principalmente a la modernización de aplicaciones existentes que normalmente tienen arquitecturas monolíticas o de N niveles.

> [!div class="step-by-step"]
> [Anterior](microsoft-technologies-in-cloud-optimized-applications.md)
> [Siguiente](deploy-existing-net-apps-as-windows-containers.md)

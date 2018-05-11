---
title: Razones para modernizar las aplicaciones existentes de .NET para aplicaciones optimizada para la nube
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Razones para modernizar las aplicaciones existentes de .NET para aplicaciones optimizada para la nube
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: a874a742f6a5b32e15040ad0a237f0e0fa7908dc
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Razones para modernizar las aplicaciones existentes de .NET para aplicaciones optimizada para la nube

Con una aplicación optimizada para la nube, puede entregar repetidamente y rápidamente aplicaciones confiables a sus clientes. Obtener agilidad esencial y la confiabilidad aplazando gran parte de la complejidad operativa de la aplicación a la plataforma.

Si no se puede obtener las aplicaciones al mercado rápidamente, por la hora de que distribuir la aplicación, habrá evolucionó hasta convertirse en el mercado que se destinatarios. Puede que sea demasiado tarde, independientemente del grado en que la aplicación se ha diseñado o ingeniería. Podrías por error o no lleguen a sus posibilidades porque no se puede sincronizar la entrega de aplicaciones con las necesidades del mercado.

La necesidad de innovación continua del negocio inserta los equipos de desarrollo y las operaciones en el límite. La única manera de lograr la agilidad que necesaria en innovación continua del negocio es modernizar las aplicaciones con tecnologías como contenedores y los principios de la aplicación optimizada para la nube específica.

La conclusión es que, cuando una organización crea y administra las aplicaciones que están optimizada para la nube, puede poner soluciones en manos de los clientes antes y poner nuevas ideas en el mercado cuando son relevantes.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Principios y principios de aplicaciones optimizada para la nube 

Mejoras en la nube se centran principalmente en cumple dos objetivos: reducir los costos y mejorar el crecimiento del negocio mediante la mejora de la agilidad. Estos objetivos se logran al simplificar procesos y reducir la fricción cuando suelte y distribuir aplicaciones.

La aplicación está optimizada para la nube si can en una herramienta ágil manera-desarrollar su aplicación de forma autónoma de otras aplicaciones locales y, a continuación, la versión, implementa, Autoescala, supervisar y solucionar problemas de la aplicación en la nube.

La clave es *agilidad*. No se puede distribuir con agilidad a menos que se reduzca al mínimo absoluto cualquier implementación de producción problemas y problemas del entorno de desarrollo y pruebas. Contenedores (específicamente, Docker, como un estándar de facto) y servicios administrados se diseñaron específicamente para este propósito.

Para lograr la agilidad, también necesita procesos automatizados de DevOps que se basan en las canalizaciones de CI/CD que vayan a plataformas escalables en la nube. Plataformas de CI/CD (por ejemplo, Visual Studio Team Services o Jenkins) que implementación en una plataforma de nube escalables y resistentes (por ejemplo, servicio de aplicaciones de Azure, Azure Service Fabric o servicio de Azure Kubernetes) son tecnologías claves para lograr la agilidad en la nube.

En la lista siguiente describe los principios principales o prácticas para aplicaciones optimizada para la nube. Tenga en cuenta que puede adoptar todos o solo algunos de estos principios en un enfoque incremental o progresivo:

-   **Contenedores**. Los contenedores proporcionan la capacidad para incluir las dependencias de aplicación a la propia aplicación. Inclusión en contenedores reduce considerablemente el número de problemas que pueden producirse cuando se implementa en entornos de producción o de prueba en entornos de ensayo. En última instancia, contenedores de mejoran la agilidad de entrega de la aplicación.

-   **En la nube resistente y escalable**. La nube proporciona una plataforma que es administrado, flexible, escalable y flexible. Estas características son fundamentales para obtener mejoras en los costos y distribuir aplicaciones de disponibles y confiables de alta en la entrega continua. Servicios administrados como bases de datos administrados, administrar almacenar en caché como un servicio (CaaS) y el almacenamiento administrado son partes fundamentales de mitigar los costos de mantenimiento de la aplicación.

-   **Supervisión**. No puede tener una aplicación confiable sin tener una buena manera de detectar y diagnosticar problemas de rendimiento de aplicación y excepciones. Debe obtener información procesable a través de administración de rendimiento de aplicaciones y análisis de la instantánea.

-   **DevOps referencia cultural y la entrega continua**. Adopción de prácticas de DevOps requiere un cambio de referencia cultural en la que los equipos ya no trabajan en silos independientes. Canalizaciones de CI/CD sólo son posibles cuando hay un aumento de la colaboración entre el desarrollo y los equipos de operaciones de TI, contenedores y herramientas de CI/CD admitidos.

Figura 4-2 muestra los principales pilares opcionales de una aplicación optimizada para la nube. Los pilares más implementar, el readier su aplicación estará sea correcta para satisfacer las expectativas de los clientes.

> ![Pilares principales de una aplicación optimizada para la nube](./media/image2.png)
>
> **Figura 4-2.** Pilares principales de una aplicación optimizada para la nube

En resumen, una aplicación optimizada para la nube es un método para crear y administrar aplicaciones que aprovecha las ventajas de la informática modelo, al usar una combinación de contenedores, infraestructura de nube administrado, técnicas de aplicación resistente, en la nube supervisión, la entrega continua y DevOps, todo ello sin necesidad de cambie la arquitectura y codificar las aplicaciones existentes.

Su organización puede adoptar estos enfoques y tecnologías gradualmente. No tienes que adoptar todas ellas, a la vez. Puede adoptar ellos de forma incremental, en función de las prioridades de la empresa y las necesidades de usuario.

## <a name="benefits-of-a-cloud-optimized-application"></a>Ventajas de una aplicación optimizada para la nube

Puede obtener las ventajas siguientes mediante la conversión de una aplicación existente a una aplicación optimizada para la nube (sin el cambio de la arquitectura o codificación):

-   **Reducir los costos, porque la infraestructura administrada se controla con el proveedor de nube**. Optimizada para la nube aplicaciones aprovechen las ventajas de la nube mediante el uso de elasticidad de la nube de fábrica, escalado automático y alta disponibilidad. Ventajas están relacionadas con no solo a las características de proceso (máquinas virtuales y contenedores), pero también dependen de recursos en la nube, como DBaaS, CaaS y cualquier infraestructura puede necesaria una aplicación.

-   **Infraestructura y las aplicaciones resistentes**. Cuando se migra a la nube, debe adoptar los errores transitorios; se producirán errores en la nube. Además, hardware y la infraestructura de nube son "reemplazables," lo que aumenta las oportunidades de tiempo de inactividad transitorio. Al mismo tiempo, capacidades de la nube interna y determinadas técnicas de desarrollo de aplicaciones que implementan la resistencia y automatizan la recuperación facilitan mucho para recuperarse de errores inesperados en la nube.

-   **Información detallada sobre el rendimiento de la aplicación**. Herramientas de supervisión como Azure Application Insights proporcionen visualización para la administración de estado, registro y las notificaciones de la nube. Los registros de auditoría hacen aplicaciones fáciles de depurar y auditoría, fundamentales para una aplicación de confianza en la nube.

-   **Portabilidad de aplicación, con las implementaciones de agile**. Los contenedores (contenedores Linux o Windows, en función de motor de Docker) ofrecen la mejor solución para evitar una aplicación bloqueada en la nube. Mediante el uso de contenedores, los hosts de Docker y orchestrators varias nubes, fácilmente puede mover desde un entorno o en la nube a otra. Contenedores de eliminan la fricción que normalmente se produce en las implementaciones en cualquier entorno (fase/prueba/producción).

En última instancia todas estas ventajas ofrecen reducciones de costos clave para el ciclo de vida de la aplicación de extremo a extremo.

En las secciones siguientes, estas ventajas se explican con más detalle y se vinculan a tecnologías específicas.

>[!div class="step-by-step"]
[Anterior](index.md)
[Siguiente](microsoft-technologies-in-cloud-optimized-applications.md)

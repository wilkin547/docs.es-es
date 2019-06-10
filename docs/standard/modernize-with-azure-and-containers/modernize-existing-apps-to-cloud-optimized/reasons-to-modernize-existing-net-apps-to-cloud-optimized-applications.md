---
title: Razones para modernizar las aplicaciones .NET existentes a las aplicaciones optimizadas para la nube
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Razones para modernizar las aplicaciones .NET existentes a las aplicaciones optimizadas para la nube
ms.date: 04/28/2018
ms.openlocfilehash: 5aa9828f65f76138461c18711fe03bdbe6a70ffd
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758748"
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Razones para modernizar las aplicaciones .NET existentes a las aplicaciones optimizadas para la nube

Con una aplicación optimizada para la nube, puede entregar varias veces y rápidamente aplicaciones confiables para sus clientes. Obtener agilidad esencial y confiabilidad aplazando gran parte de la complejidad operativa de la aplicación a la plataforma.

Si no se puede obtener sus aplicaciones al mercado rápidamente, en el momento en que envíe su aplicación, el mercado que objetivo fueran habrá evolucionado. Podría ser demasiado tarde, con independencia de lo bien la aplicación se ha diseñado o ingeniería. Puede se producen errores o no alcanzar todo su potencial porque no se pueden sincronizar la entrega de aplicaciones con las necesidades del mercado.

La necesidad de innovación continua comercial inserta los equipos de desarrollo y las operaciones en el límite. Es la única manera de lograr la agilidad que necesaria en la innovación continua del negocio mediante la modernización de las aplicaciones con tecnologías como contenedores y los principios de la aplicación optimizada para la nube específica.

La conclusión es que cuando una organización crea y administra las aplicaciones que están optimizadas para la nube, puede colocar las soluciones en manos de los clientes antes y aportar nuevas ideas al mercado cuando son relevantes.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Principios y los principios de la aplicación optimizada para la nube 

Mejoras en la nube se centran principalmente en cumple dos objetivos: Reducir los costos y mejorar el crecimiento del negocio al mejorar la agilidad. Estos objetivos se consiguen al simplificar los procesos y reducir la fricción cuando se libera y distribuir las aplicaciones.

La aplicación está optimizada para la nube si can en la aplicación autónoma desde otras aplicaciones locales de manera desarrollar una herramienta ágil y suéltelo, implementa, el escalado automático, supervisar y solucionar problemas de la aplicación en la nube.

La clave es *agilidad*. No se puede distribuir con agilidad, a menos que reduzca al mínimo absoluto cualquier implementación de producción problemas y problemas del entorno de desarrollo y pruebas. Contenedores (en concreto, Docker, como un estándar de facto) y los servicios administrados se diseñaron específicamente para este propósito.

Para lograr la agilidad, también necesita procesos automatizados de DevOps que se basan en las canalizaciones de CI/CD que liberan a plataformas escalables en la nube. Las plataformas de CI/CD (como Azure DevOps Services o Jenkins) que implementa en una plataforma de nube escalable y resistente (como Azure App Service o Azure Kubernetes Service) son tecnologías clave para lograr la agilidad en la nube.

La lista siguiente describe los principios principales o prácticas para las aplicaciones optimizadas para la nube. Tenga en cuenta que puede adoptar todas o solo algunos de estos principios en un enfoque incremental o progresivo:

- **Contenedores**. Los contenedores ofrecen la posibilidad de incluir las dependencias de aplicación con la propia aplicación. Inclusión en contenedores reduce considerablemente el número de problemas que pueden producirse al implementar en entornos de producción o de prueba en entornos de ensayo. En última instancia, contenedores de mejoran la agilidad de entrega de aplicaciones.

- **En la nube escalable y resistente**. La nube proporciona una plataforma que sea administrado, flexible, escalable y resistente. Estas características son fundamentales para obtener mejoras en los costos y distribuir alta disponibilidad y confiabilidad de las aplicaciones en una entrega continua. Servicios administrados como bases de datos administrados, administra almacenar en caché como un servicio (CaaS) y el almacenamiento administrado son los componentes fundamentales aliviar los costos de mantenimiento de la aplicación.

- **Supervisión**. No puede tener una aplicación confiable sin tener una buena forma de detectar y diagnosticar excepciones y problemas de rendimiento de aplicaciones. Deberá obtener conocimiento a través de la administración del rendimiento de aplicación y el análisis instantáneo.

- **DevOps referencia cultural y la entrega continua**. Adoptar prácticas de DevOps, requiere un cambio cultural en el que los equipos ya no trabajan en silos independientes. Canalizaciones de CI/CD sólo son posibles cuando hay un aumento de la colaboración entre el desarrollo y los equipos de operaciones de TI, compatibles con contenedores y herramientas CI/CD.

Figura 4-2 se muestran los principales pilares opcionales de una aplicación optimizada para la nube. Los pilares más implementa, el readier la aplicación estará triunfar en cumple las expectativas de sus clientes.

> ![Pilares principales de una aplicación optimizada para la nube](./media/image2.png)
>
> **Figura 4-2.** Pilares principales de una aplicación optimizada para la nube

En resumen, una aplicación optimizada para la nube es un enfoque para crear y administrar aplicaciones que aprovecha las ventajas de informática de modelo, al usar una combinación de contenedores, infraestructura en la nube administrado, las técnicas de aplicaciones resistentes, en la nube supervisión, la entrega continua y DevOps, todo ello sin necesidad de rediseñar y codificar las aplicaciones existentes.

Su organización puede adoptar estas tecnologías y enfoques gradualmente. No debe adoptar todas ellas, a la vez. Que puede adoptarlas incrementalmente, según las prioridades empresariales y necesidades de los usuarios.

## <a name="benefits-of-a-cloud-optimized-application"></a>Ventajas de una aplicación optimizada para la nube

Puede obtener mediante la conversión de una aplicación existente a una aplicación optimizada para la nube (sin necesidad de rediseñar o codificación) las siguientes ventajas:

- **Reducir los costes, ya que la infraestructura administrada se controla mediante el proveedor de nube**. Aplicaciones optimizadas para la nube obtienen las ventajas de la nube mediante el uso de elasticidad de la nube de fábrica, el escalado automático y alta disponibilidad. Ventajas están relacionadas no solo a las características de proceso (máquinas virtuales y contenedores), pero también dependen de los recursos en la nube, como DBaaS, CaaS y cualquier infraestructura de una aplicación es posible que sea necesario.

- **Infraestructura y aplicaciones resistentes**. Al migrar a la nube, deberá adoptar los errores transitorios se producirán errores en la nube. Además, hardware y la infraestructura de nube son "reemplazables," lo que aumenta las oportunidades de tiempo de inactividad transitorio. Al mismo tiempo, las capacidades de nube interna y determinadas técnicas de desarrollo de aplicaciones que implementan la resistencia y automatizan la recuperación facilitan mucho más fácil para recuperarse de errores inesperados en la nube.

- **Información detallada sobre el rendimiento de la aplicación**. En la nube las herramientas de supervisión, como Azure Application Insights proporciona visualización de notificaciones, registro y administración de la salud. Los registros de auditoría que aplicaciones fácil depurar y auditoría, es fundamental para una aplicación en la nube confiable.

- **Portabilidad de aplicaciones, con las implementaciones de agile**. Los contenedores (contenedores Linux o Windows, según el motor de Docker) ofrecen la mejor solución para evitar una aplicación bloqueada en la nube. Fácilmente mediante el uso de contenedores, los hosts de Docker y orquestadores de varias nubes, puede mover de un entorno o en la nube a otra. Los contenedores eliminan la fricción que normalmente se produce en las implementaciones en cualquier entorno (fase, prueba y producción).

Todas estas ventajas proporcionan en última instancia reducciones de costos importante para el ciclo de vida de aplicación to-end.

En las secciones siguientes, estas ventajas se explican con más detalle y se vinculan a tecnologías específicas.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](microsoft-technologies-in-cloud-optimized-applications.md)

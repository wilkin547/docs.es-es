---
title: Razones para elevar y cambiar existente de aplicaciones .NET para aplicaciones de uso de DevOps en la nube
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Razones para elevar y cambiar existente de aplicaciones .NET para aplicaciones de uso de DevOps en la nube
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4f09ec8f5aa041057ac1256eb564e197793c8a2b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications"></a>Razones para elevar y cambiar existente de aplicaciones .NET para aplicaciones de uso de DevOps en la nube

Con una aplicación preparada para DevOps la nube, puede entregar repetidamente y rápidamente aplicaciones confiables a sus clientes. Obtener agilidad esencial y la confiabilidad aplazando gran parte de la complejidad operativa de la aplicación a la plataforma.

Si no se puede obtener las aplicaciones al mercado rápidamente, por la hora de que distribuir la aplicación, habrá evolucionó hasta convertirse en el mercado que se destinatarios. Puede que sea demasiado tarde, independientemente del grado en que la aplicación se ha diseñado o ingeniería. Podrías por error o no lleguen a sus posibilidades porque no se puede sincronizar la entrega de aplicaciones con las necesidades del mercado.

La necesidad de innovación continua del negocio inserta los equipos de desarrollo y las operaciones en el límite. La única manera de lograr la agilidad que necesaria en innovación continua del negocio es modernizar las aplicaciones con tecnologías como contenedores y principios de aplicación preparada para DevOps la nube específicos.

La conclusión es que cuando una organización crea y administra las aplicaciones que están listas para DevOps en la nube, puede poner soluciones en manos de los clientes antes y dar ideas nueva en el mercado cuando son relevantes.

## <a name="cloud-devops-ready-application-principles-and-tenets"></a>Principios de aplicaciones de nube DevOps listo y principios 

Mejoras en la nube se centran principalmente en cumple dos objetivos: reducir los costos y mejorar el crecimiento del negocio mediante la mejora de la agilidad. Estos objetivos se logran al simplificar procesos y reducir la fricción cuando suelte y distribuir aplicaciones.

La aplicación está preparada para DevOps la nube si se puede en un agile manera-desarrollar su aplicación de forma autónoma de otras aplicaciones locales y, a continuación, la versión, implementar, Autoescala, supervisar y solucionar problemas de la aplicación en la nube.

La clave es *agilidad*. No se puede distribuir con agilidad a menos que se reduzca al mínimo absoluto cualquier implementación de producción problemas y problemas del entorno de desarrollo y pruebas. Contenedores (específicamente, Docker, como un estándar de facto) y servicios administrados se diseñaron específicamente para este propósito.

Para lograr la agilidad, también necesita procesos automatizados de DevOps que se basan en las canalizaciones de CI/CD que vayan a plataformas escalables en la nube. Plataformas de CI/CD (por ejemplo, Visual Studio Team Services o Jenkins) que implementación en una plataforma de nube escalables y resistentes (por ejemplo, Azure Service Fabric o Kubernetes) son tecnologías claves para lograr la agilidad en la nube.

En la lista siguiente describe los principios principales o prácticas para aplicaciones de uso de DevOps en la nube. Tenga en cuenta que puede adoptar todos o solo algunos de estos principios en un enfoque incremental o progresivo:

-   **Contenedores**. Los contenedores proporcionan la capacidad para incluir las dependencias de aplicación a la propia aplicación. Inclusión en contenedores reduce considerablemente el número de problemas que pueden producirse cuando se implementa en entornos de producción o de prueba en entornos de ensayo. En última instancia, contenedores de mejoran la agilidad de entrega de la aplicación.

-   **En la nube resistente y escalable**. La nube proporciona una plataforma que es administrado, flexible, escalable y flexible. Estas características son fundamentales para obtener mejoras en los costos y distribuir aplicaciones de disponibles y confiables de alta en la entrega continua. Servicios administrados como bases de datos administrados, administrar almacenar en caché como un servicio (CaaS) y el almacenamiento administrado son partes fundamentales de mitigar los costos de mantenimiento de la aplicación.

-   **Supervisión**. No puede tener una aplicación confiable sin tener una buena manera de detectar y diagnosticar problemas de rendimiento de aplicación y excepciones. Debe obtener información procesable a través de administración de rendimiento de aplicaciones y análisis de la instantánea.

-   **DevOps referencia cultural y la entrega continua**. Adopción de prácticas de preparada para DevOps la nube requiere un cambio de referencia cultural en la que los equipos ya no trabajan en silos independientes. Canalizaciones de CI/CD sólo son posibles cuando hay un aumento de la colaboración entre el desarrollo y los equipos de operaciones de TI, contenedores y herramientas de CI/CD admitidos.

Figura 4-2 muestra los principales pilares opcionales de una aplicación preparada para DevOps la nube. Los pilares más implementar, el readier su aplicación estará sea correcta para satisfacer las expectativas de los clientes.

> ![Pilares principales de una aplicación preparada para DevOps la nube](./media/image2.png)
>
> **Figura 4-2.** Pilares principales de una aplicación preparada para DevOps la nube

En resumen, una aplicación preparada para DevOps la nube es un método para crear y administrar aplicaciones que aprovecha las ventajas de la informática modelo, al usar una combinación de contenedores, infraestructura de nube administrado, técnicas de aplicación resistente, en la nube supervisión, la entrega continua y DevOps, todo ello sin necesidad de volver a diseñar y codificar las aplicaciones existentes.

Su organización puede adoptar estos enfoques y tecnologías gradualmente. No tienes que adoptar todas ellas, a la vez. Puede adoptar ellos de forma incremental, en función de las prioridades de la empresa y las necesidades de usuario.

## <a name="benefits-of-a-cloud-devops-ready-application"></a>Ventajas de una aplicación preparada para DevOps la nube

Puede obtener las ventajas siguientes mediante la conversión de una aplicación existente a una aplicación preparada para DevOps la nube (sin volver a diseñar o codificación):

-   **Reducir los costos, porque la infraestructura administrada se controla con el proveedor de nube**. Aplicaciones de uso de DevOps de nube aprovechen las ventajas de la nube mediante el uso de elasticidad de la nube de fábrica, escalado automático y alta disponibilidad. Ventajas están relacionadas con no solo a las características de proceso (máquinas virtuales y contenedores), pero también dependen de recursos en la nube, como DBaaS, CaaS y cualquier infraestructura puede necesaria una aplicación.

-   **Infraestructura y las aplicaciones resistentes**. Cuando se migra a la nube, debe adoptar los errores transitorios; se producirán errores en la nube. Además, hardware y la infraestructura de nube es "reemplazables," lo que aumenta las oportunidades de tiempo de inactividad transitorio. Al mismo tiempo, capacidades de la nube interna y determinadas técnicas de desarrollo de aplicaciones que implementan la resistencia y automatizan la recuperación facilitan mucho para recuperarse de errores inesperados en la nube.

-   **Información detallada sobre el rendimiento de la aplicación**. Herramientas de supervisión como Azure Application Insights proporcionen visualización para la administración de estado, registro y las notificaciones de la nube. Hacer que las aplicaciones fáciles de depurar y la auditoría de registros de auditoría. Esto es fundamental para una aplicación de confianza en la nube.

-   **Portabilidad de aplicación, con las implementaciones de agile**. Los contenedores (contenedores Linux o Windows, en función de motor de Docker) ofrecen la mejor solución para evitar una aplicación bloqueada en la nube. Mediante el uso de contenedores, los hosts de Docker y orchestrators varias nubes, fácilmente puede mover desde un entorno o en la nube a otra. Contenedores de eliminan la fricción que normalmente se produce en las implementaciones en cualquier entorno (fase/prueba/producción).

En última instancia todas estas ventajas ofrecen reducciones de costos clave para el ciclo de vida de la aplicación de extremo a extremo.

En las secciones siguientes, estas ventajas se explican con más detalle y se vinculan a tecnologías específicas.

>[!div class="step-by-step"]
[Anterior](index.md)
[Siguiente](microsoft-technologies-in-cloud-devops-ready-applications.md)

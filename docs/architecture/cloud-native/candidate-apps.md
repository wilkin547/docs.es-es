---
title: Aplicaciones candidatas para la nube nativa
description: Obtenga información sobre los tipos de aplicaciones que se benefician de un enfoque nativo en la nube
author: robvet
ms.date: 05/14/2020
ms.openlocfilehash: b907a17b2351bc4ffe49fd6eb6f5963b209d00db
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614245"
---
# <a name="candidate-apps-for-cloud-native"></a>Aplicaciones candidatas para la nube nativa

Examine las aplicaciones de su cartera. ¿Cuántos de ellos son aptas para una arquitectura nativa en la nube? ¿Todos ellos? ¿Quizás alguna?

Al aplicar un análisis de costos y beneficios, existe la posibilidad de que la mayoría de ellas no admita la etiqueta de precio de alto nivel que se requiere para ser nativa en la nube. El costo de ser nativo en la nube superaría mucho el valor empresarial de la aplicación.

¿Qué tipo de aplicación puede ser un candidato para la nube nativa?

- Sistema estratégico de empresa que necesita desarrollar constantemente funcionalidades y características empresariales

- Una aplicación que requiere una velocidad de lanzamiento alta, con alta confianza

- Sistema con el que las características individuales deben liberarse *sin necesidad* de una reimplementación completa de todo el sistema.

- Una aplicación desarrollada por los equipos con experiencia en diferentes pilas de tecnología

- Una aplicación con componentes que deben escalarse de forma independiente

A continuación, hay sistemas heredados. Aunque nos gustaría crear nuevas aplicaciones, a menudo nos responsabilizaremos de modernizar las cargas de trabajo heredadas que son críticas para el negocio. Con el tiempo, una aplicación heredada se puede descomponer en microservicios, en contenedores y en última instancia en una arquitectura nativa en la nube.

### <a name="modernizing-legacy-apps"></a>Modernización de aplicaciones heredadas

El libro electrónico gratuito de Microsoft [modernizar las aplicaciones .net existentes con la nube de Azure y los contenedores de Windows](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) proporciona instrucciones para migrar cargas de trabajo locales a la nube. En la figura 1-10 se muestra que no hay una estrategia única y única para la modernización de aplicaciones heredadas.

![Estrategias para migrar cargas de trabajo heredadas](./media/strategies-for-migrating-legacy-workloads.png)

**Figura 1-10**. Estrategias para migrar cargas de trabajo heredadas

Las aplicaciones monolíticas que no son críticas se benefician en gran medida de una migración rápida de elevación y desplazamiento ([lista para la infraestructura en la nube](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)). En este caso, la carga de trabajo local se hospeda en una máquina virtual en la nube, sin cambios. Este enfoque utiliza el [modelo de IaaS (infraestructura como servicio)](https://azure.microsoft.com/overview/what-is-iaas/). Azure incluye varias herramientas, como [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/)y [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) para facilitar este movimiento. Aunque esta estrategia puede producir un ahorro de costos, estas aplicaciones no se diseñaron normalmente para desbloquear y aprovechar las ventajas de la informática en la nube.

Las aplicaciones monolíticas que son críticas para el negocio a menudo se benefician de una migración mejorada de elevación y desplazamiento (*optimizada*para la nube). Este enfoque incluye optimizaciones de implementación que habilitan los servicios en la nube clave, sin cambiar la arquitectura básica de la aplicación. Por ejemplo, podría incluir la aplicación en un [contenedor](https://docs.microsoft.com/virtualization/windowscontainers/about/) e implementarla en un orquestador de contenedores, como [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), que se describe más adelante en este libro. Una vez en la nube, la aplicación podría consumir otros servicios en la nube, como bases de datos, colas de mensajes, supervisión y almacenamiento en caché distribuida.

Por último, las aplicaciones monolíticas que realizan funciones estratégicas de empresa podrían beneficiarse mejor de un enfoque nativo de la *nube* , el asunto de este libro. Este enfoque proporciona agilidad y velocidad. Pero se trata de un costo de replataforma, rediseño y reescritura de código.

Si usted y su equipo creen que un enfoque nativo de la nube es adecuado, le conviene racionalizar la decisión con su organización. ¿Qué es exactamente el problema empresarial que resolverá un enfoque nativo en la nube? ¿Cómo se alinearía con las necesidades empresariales?

- Versiones rápidas de características con mayor confianza

- Escalabilidad específica: uso más eficaz de los recursos

- ¿Mejora la resistencia del sistema?

- ¿Mejoró el rendimiento del sistema?

- ¿Más visibilidad de las operaciones?

- Las plataformas de desarrollo de Blend y los almacenes de datos para llegar a la mejor herramienta para el trabajo?

- ¿Inversión en aplicaciones en el futuro?

La estrategia de migración adecuada depende de las prioridades de la organización y de los sistemas de destino. Para muchos, puede ser más rentable para optimizar en la nube una aplicación monolítica o agregar servicios generales a una aplicación de N niveles. En estos casos, todavía puede hacer uso completo de las funcionalidades de PaaS en la nube, como las que ofrecen Azure App Service.

## <a name="summary"></a>Resumen

En este capítulo, se presentó la informática nativa en la nube. Hemos proporcionado una definición junto con las funcionalidades clave que controlan una aplicación nativa en la nube. Analizamos los tipos de aplicaciones que podrían justificar esta inversión y esfuerzo.

Con la introducción, ahora profundizaremos en una mirada mucho más detallada en la nube nativa.

### <a name="references"></a>Referencias

- [Base informática nativa en la nube](https://www.cncf.io/)

- [Microservicios de .NET: arquitectura para aplicaciones .NET en contenedor](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Modernización de aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [Patrones nativos en la nube de Cornelia Davis](https://www.manning.com/books/cloud-native-patterns)

- [Más allá de la aplicación de doce factores](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [Qué es la infraestructura como código](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [Micro deploy de ingeniería de uber: implementación diaria con confianza](https://eng.uber.com/micro-deploy/)

- [Cómo implementa Netflix el código](https://www.infoq.com/news/2013/06/netflix/)

- [Control de sobrecarga para el escalado de microservicios WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[Anterior](definition.md)
>[Siguiente](introduce-eshoponcontainers-reference-app.md)

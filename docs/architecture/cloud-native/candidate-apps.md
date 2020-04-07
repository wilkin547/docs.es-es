---
title: Aplicaciones candidatas para nativos de la nube
description: Conozca qué tipos de aplicaciones se benefician de un enfoque nativo de la nube
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805615"
---
# <a name="candidate-apps-for-cloud-native"></a>Aplicaciones candidatas para nativos de la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Mira las aplicaciones de tu portafolio. ¿Cuántos de ellos califican para una arquitectura nativa de la nube? ¿Todos ellos? ¿Quizás algo?

Al aplicar un análisis de costo/beneficio, existe una buena probabilidad de que la mayoría no admita la etiqueta de precio considerable necesaria para ser nativo de la nube. El costo de ser nativo de la nube superaría con creces el valor empresarial de la aplicación.

¿Qué tipo de aplicación podría ser un candidato para nativo de la nube?

- Un sistema empresarial grande y estratégico que necesita evolucionar constantemente las capacidades/características del negocio

- Una aplicación que requiere una alta velocidad de liberación - con alta confianza

- Un sistema con características individuales deben liberarse *sin* una redistribución completa de todo el sistema

- Una aplicación desarrollada por equipos con experiencia en diferentes pilas de tecnología

- Una aplicación con componentes que deben escalar de forma independiente

Luego hay sistemas heredados. Aunque a todos nos gustaría crear nuevas aplicaciones, a menudo somos responsables de modernizar las cargas de trabajo heredadas que son fundamentales para el negocio. Con el tiempo, una aplicación heredada podría descomponerse en microservicios, en contenedores y, en última instancia, "replataforma" en una arquitectura nativa de la nube.

### <a name="modernizing-legacy-apps"></a>Modernización de aplicaciones heredadas

El libro electrónico gratuito de Microsoft [Moderniza las aplicaciones .NET existentes con Azure Cloud y Contenedores](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) de Windows proporciona instrucciones para migrar cargas de trabajo locales a la nube. La Figura 1-10 muestra que no hay una estrategia única y única para modernizar las aplicaciones heredadas.

![Estrategias para migrar cargas de trabajo heredadas](./media/strategies-for-migrating-legacy-workloads.png)

**Figura 1-10**. Estrategias para migrar cargas de trabajo heredadas

Las aplicaciones monolíticas que no son críticas se benefician en gran medida de una rápida migración de elevación y desplazamiento[(preparada para](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)la infraestructura en la nube). Aquí, la carga de trabajo local se vuelve a hospedar en una máquina virtual basada en la nube, sin cambios. Este enfoque utiliza el [modelo IaaS (Infraestructura como servicio).](https://azure.microsoft.com/overview/what-is-iaas/) Azure incluye varias herramientas, como [Azure Migrate,](https://azure.microsoft.com/services/azure-migrate/) [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/)y Azure Database Migration [Service,](https://azure.microsoft.com/campaigns/database-migration/) para facilitar dicho movimiento. Si bien esta estrategia puede producir algunos ahorros de costos, estas aplicaciones normalmente no se diseñaron para desbloquear y aprovechar los beneficios de la computación en la nube.

Las aplicaciones monolíticas que son fundamentales para el negocio a menudo se benefician de una migración mejorada de elevación y desplazamiento (optimizada en la*nube).* Este enfoque incluye optimizaciones de implementación que habilitan los servicios clave en la nube, sin cambiar la arquitectura principal de la aplicación. Por ejemplo, puede [contener](https://docs.microsoft.com/virtualization/windowscontainers/about/) la aplicación e implementarla en un orquestador de [contenedores, como Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), que se describe más adelante en este libro. Una vez en la nube, la aplicación podría consumir otros servicios en la nube, como bases de datos, colas de mensajes, supervisión y almacenamiento en caché distribuido.

Por último, las aplicaciones monolíticas que realizan funciones empresariales estratégicas podrían beneficiarse mejor de un enfoque *nativo* de la nube, el tema de este libro. Este enfoque proporciona agilidad y velocidad. Sin más que, tiene un costo de replataforma, rearquitectura y reescritura de código.

Si usted y su equipo creen que un enfoque nativo de la nube es apropiado, le corresponde racionalizar la decisión con su organización. ¿Cuál es exactamente el problema empresarial que resolverá un enfoque nativo de la nube? ¿Cómo se alinearía con las necesidades del negocio?

- ¿Lanzamientos rápidos de características con mayor confianza?

- Escalabilidad detallada: ¿un uso más eficiente de los recursos?

- ¿Mejora de la resiliencia del sistema?

- ¿Mejora del rendimiento del sistema?

- ¿Más visibilidad de las operaciones?

- ¿Combina plataformas de desarrollo y almacenes de datos para llegar a la mejor herramienta para el trabajo?

- ¿Inversión de solicitud a prueba de futuro?

La estrategia de migración correcta depende de las prioridades organizativas y de los sistemas a los que se dirige. Para muchos, puede ser más rentable optimizar en la nube una aplicación monolítica o agregar servicios de grano grueso a una aplicación de nivel N. En estos casos, todavía puede hacer uso completo de las funcionalidades de PaaS en la nube, como las que ofrece Azure App Service.

## <a name="summary"></a>Resumen

En este capítulo, introdujimos la informática nativa de la nube. Proporcionamos una definición junto con las capacidades clave que impulsan una aplicación nativa de la nube. Examinamos los tipos de solicitudes que podrían justificar esta inversión y esfuerzo.

Con la introducción detrás, ahora nos sumergimos en una mirada mucho más detallada a la nube nativa.

### <a name="references"></a>Referencias

- [Cloud Native Computing Foundation](https://www.cncf.io/)

- [Microservicios de .NET: arquitectura para aplicaciones .NET en contenedores](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Modernice las aplicaciones .NET existentes con Azure Cloud y Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [Cloud Native Patterns de Cornelia Davis](https://www.manning.com/books/cloud-native-patterns)

- [Más allá de la aplicación de doce factores](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [Qué es la infraestructura como código](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [Micro Deploy de Uber Engineering: Implementación diaria con confianza](https://eng.uber.com/micro-deploy/)

- [Cómo Netflix implementa el código](https://www.infoq.com/news/2013/06/netflix/)

- [Control de sobrecarga para escalar microservicios de WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[Anterior](definition.md)
>[Siguiente](introduce-eshoponcontainers-reference-app.md)

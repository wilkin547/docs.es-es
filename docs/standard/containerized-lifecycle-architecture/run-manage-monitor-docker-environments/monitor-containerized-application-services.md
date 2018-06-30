---
title: Supervisar los servicios de aplicaciones en contenedores
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 368d99e92f80cf37965139cb67fc5f22b44f40cd
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106141"
---
# <a name="monitor-containerized-application-services"></a>Supervisar los servicios de aplicaciones en contenedores

Es fundamental para las aplicaciones que se divide en varios contenedores y microservicios tiene una manera de supervisar y analizar el comportamiento de la aplicación.

## <a name="microsoft-application-insights"></a>Visión de la aplicación de Microsoft

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) es un servicio de análisis extensible que supervisa su aplicación en vivo. Puede ayudarle a detectar y diagnosticar problemas de rendimiento y a comprender lo que los usuarios hacer con la aplicación. Está diseñado para los desarrolladores, con el propósito de ayudar a mejorar continuamente el rendimiento y facilidad de uso de los servicios o aplicaciones. Visión de la aplicación funciona con/servicios web e independiente aplicaciones en una amplia variedad de plataformas como. NET, Java, Node.js y muchas otras plataformas, habían hospedado en local o en la nube.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Analizar aplicaciones de Docker en entornos de preguntas y respuestas con Application Insights

Ya que pertenece a Docker, puede realizar un gráfico eventos de ciclo de vida y contadores de rendimiento de los contenedores de Docker en la información de la aplicación. Solo tiene que ejecutar el [imagen de aplicación visión Docker](https://hub.docker.com/r/microsoft/applicationinsights/) como un contenedor en el host y muestra los contadores de rendimiento para el host, así como para las otras imágenes de Docker. Esta imagen de Docker de información de aplicación (figura 6 - 1) le ayuda a supervisar las aplicaciones en contenedores mediante la recopilación de telemetría acerca del rendimiento y la actividad de su host de Docker (es decir, las máquinas virtuales de Linux), los contenedores de Docker y las aplicaciones se ejecutan dentro de ellos.

![ejemplo](./media/image1.png)

Figura 6-1: Application Insights supervisión contenedores y los hosts de Docker

Al ejecutar el [imagen de aplicación visión Docker](https://hub.docker.com/r/microsoft/applicationinsights/) en el host Docker, beneficiarse de las siguientes:

-   Ciclo de vida de telemetría acerca de todos los contenedores que se ejecutan en el host: iniciar, detener y así sucesivamente.

-   Contadores de rendimiento para todos los contenedores: CPU, memoria, uso de la red y mucho más.

-   Si instaló también [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) en las aplicaciones que se ejecutan en los contenedores, todas la telemetría de esas aplicaciones tendrán propiedades adicionales que identifica el equipo de contenedor y el host. Por lo tanto, por ejemplo, si tiene instancias de aplicaciones que se ejecutan en más de un host, fácilmente podrá filtrar la telemetría de aplicación host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Configuración de Application Insights para supervisar las aplicaciones de Docker y hosts de Docker

Para crear un recurso de Application Insights, siga las instrucciones que aparecen en los artículos que se presentan en la lista que sigue. Portal de Azure creará el script necesario para usted.

-   **Supervisar las aplicaciones de Docker de Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Imagen de Docker de visión de la aplicación en Docker Hub y Github:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) y <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Configure información de aplicación de ASP.NET:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights para páginas web:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](http://microsoft.com/oms) es una solución de administración simplificada de TI que proporciona análisis de registros, la automatización, la copia de seguridad y recuperación del sitio. En función de [consultas](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) en Operations Management Suite, puede generar [alertas](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) y establezca la corrección a través de [automatización de Azure](https://docs.microsoft.com/azure/automation/). Perfectamente también se integra con las soluciones de administración existente para proporcionar una sola vista de panel de vidrio. Operations Management Suite puede ayudarle a administrar y proteger el entorno local y la nube de infraestructura.

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](http://microsoft.com/oms) soluciones de contenedor de Docker

Además de ofrecer servicios valiosos por sí mismo, la solución de contenedor de Operations Management Suite puede administrar y supervisar los hosts de Docker y contenedores mostrando información acerca de que los contenedores y los hosts de contenedor, que se están ejecutando contenedores o con error y los registros de demonio y contenedor de Docker enviados a *stdout* y *stderr*. También muestra las métricas de rendimiento, como la CPU, la memoria, la red y el almacenamiento del contenedor y los hosts, para ayudar a solucionar problemas y detectar contenedores próximos ruidosos.

![](./media/image2.png)

Figura 6-2: información acerca de los contenedores de Docker que se muestra por Operations Management Suite

Application Insights y Operations Management Suite se centran en la supervisión de las actividades; Sin embargo, Application Insights se centra más en la supervisión de las aplicaciones por sí mismos gracias a su SDK que se ejecuta dentro de la aplicación. Sin embargo, Operations Management Suite se centra mucho más en la infraestructura en torno a los hosts más ofrece un análisis profundo en registros en escala al proporcionar un sistema muy flexible de búsqueda o consulta controlada por datos.

Debido a Operations Management Suite se implementa como un servicio basado en la nube, se puede hacer que a trabajar rápidamente con una mínima inversión en servicios de infraestructura. Características nuevas se entregan automáticamente, lo que evita un mantenimiento continuado y costos de actualización.

Con la solución de contenedor de Operations Management Suite, puede hacer lo siguiente:

-   Centralizar y correlacionar millones de registros de contenedores de Docker a escala

-   Ver información acerca de todos los hosts de contenedor en una única ubicación

-   Saber qué contenedores están ejecutando, la imagen que se ejecutan y donde se está ejecutando

-   Diagnosticar rápidamente los contenedores de "vecino ruidoso" que pueden causar problemas en los hosts de contenedor

-   Vea una pista de auditoría de acciones en los contenedores

-   Solucionar problemas mediante la visualización y búsqueda de registros centralizados sin conexión remota para los hosts de Docker

-   Buscar contenedores que podrían ser "vecinos con ruido" y consumo exceso de recursos en un host

-   Ver centralizada CPU, memoria, almacenamiento e información de uso y rendimiento de red para contenedores

-   Generar pruebas contenedores de Docker con automatización de Azure

Puede ver información sobre el rendimiento mediante la ejecución de consultas como tipo = Perf, tal como se muestra en la figura 6-3.

![DockerPerfMetricsView](./media/image3.png){width = "5.78625 en" height = "3,25 en"}

Figura 6-3: las métricas de rendimiento de hosts de Docker que se muestra por Operations Management Suite

Guardar las consultas también es una característica estándar en Operations Management Suite y puede ayudarle a mantener las consultas que haya encontrado útil y detecta las tendencias en el sistema.

**Obtener más información** para buscar información sobre cómo instalar y configurar el Docker soluciones de contenedor en [Operations Management Suite](http://microsoft.com/oms), vaya a <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.

>[!div class="step-by-step"]
[Anterior](manage-production-docker-environments.md)
[Siguiente](../key-takeaways/index.md)

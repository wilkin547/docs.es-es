---
title: Supervisar los servicios de aplicación en contenedor
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4bdc4470624ce6e905ab858a2bd8b607c8d3d646
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47232929"
---
# <a name="monitor-containerized-application-services"></a>Supervisar los servicios de aplicación en contenedor

Es fundamental para las aplicaciones que se divide en varios contenedores y microservicios tiene una forma de supervisar y analizar el comportamiento de la aplicación.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) es un servicio de análisis extensible que supervisa la aplicación activa. Le ayuda a detectar y diagnosticar problemas de rendimiento y comprender lo que los usuarios hacen con su aplicación. Está diseñado para desarrolladores, con la intención de ayudarle a mejorar continuamente el rendimiento y facilidad de uso de los servicios o aplicaciones. Application Insights funciona con/servicios web e independiente de aplicaciones en una amplia variedad de plataformas como. NET, Java, Node.js y muchas otras plataformas, hospedadas en local o en la nube.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Análisis de aplicaciones de Docker en entornos de preguntas y respuestas con Application Insights

Lo que respecta a Docker, podrá crear un gráfico eventos de ciclo de vida y los contadores de rendimiento de los contenedores de Docker en Application Insights. Deberá ejecutar el [imagen de Docker de Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) como un contenedor en el host y se mostrarán los contadores de rendimiento para el host, así como para las demás imágenes de Docker. Esta imagen de Docker de Application Insights (figura 6 - 1) le ayuda a supervisar sus aplicaciones de contenedor mediante la recopilación de datos de telemetría sobre el rendimiento y la actividad de su host de Docker (es decir, las máquinas virtuales de Linux), los contenedores de Docker y las aplicaciones que se ejecutan dentro de ellos.

![ejemplo](./media/image1.png)

Figura 6-1: Application Insights, supervisión de contenedores y los hosts de Docker

Al ejecutar el [imagen de Docker de Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) en el host de Docker, beneficiarse de las siguientes:

-   Datos de telemetría sobre todos los contenedores que se ejecutan en el host de ciclo de vida, iniciar, detener y así sucesivamente.

-   Contadores de rendimiento para todos los contenedores: CPU, memoria, uso de la red y mucho más.

-   Si también ha instalado [SDK de Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) en las aplicaciones que se ejecutan en los contenedores, toda la telemetría de dichas aplicaciones tendrán propiedades adicionales que identifiquen el contenedor y el equipo host. Por lo tanto, por ejemplo, si tiene instancias de una aplicación que se ejecuta en más de un host, fácilmente podrá filtrar los datos de telemetría de aplicación por host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Configuración de Application Insights para supervisar aplicaciones de Docker y los hosts de Docker

Para crear un recurso de Application Insights, siga las instrucciones en los artículos que se presentan en la lista siguiente. Portal de Azure creará el script necesario para usted.

-   **Supervisar aplicaciones Docker en Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Imagen de Docker de la información de la aplicación en Docker Hub y Github:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) Y <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **Configurar Application Insights para ASP.NET:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **Application Insights para páginas web:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](https://microsoft.com/oms) es una solución de administración de TI simplificada que ofrece log analytics, automation, backup y site recovery. En función de [consultas](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) en Operations Management Suite, se puede provocar [alertas](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) y establezca la corrección mediante [Azure Automation](https://docs.microsoft.com/azure/automation/). Se integra también perfectamente con las soluciones de administración existentes para proporcionar una vista de panel de vidrio única. Operations Management Suite le ayuda a administrar y proteger sus instalaciones y la infraestructura en la nube.

### <a name="operations-management-suitehttpsmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](https://microsoft.com/oms) solución de contenedor de Docker

Además de proporcionar servicios valiosos por sí mismo, la solución de contenedor de Operations Management Suite puede administrar y supervisar los hosts de Docker y contenedores mostrando información acerca de donde los contenedores y los hosts de contenedores, qué contenedores se están ejecutando o con errores y Docker daemon y contenedor de los registros enviados a *stdout* y *stderr*. También muestra las métricas de rendimiento, como la CPU, la memoria, la red y el almacenamiento del contenedor y los hosts, para ayudar a solucionar problemas y detectar contenedores próximos ruidosos.

![](./media/image2.png)

Figura 6-2: información acerca de los contenedores de Docker que se muestra por Operations Management Suite

Application Insights y Operations Management Suite se centran en la supervisión de actividades. Sin embargo, Application Insights se centra más en las aplicaciones ellos mismos gracias a su SDK que se ejecutan dentro de la aplicación de supervisión. Sin embargo, Operations Management Suite se centra mucho más en la infraestructura en torno a los hosts, y ofrece un análisis profundo de los registros a escala al tiempo que proporciona un sistema muy flexible de búsqueda o consulta controlada por datos.

Dado que Operations Management Suite se implementa como un servicio basado en la nube, se puede hacer que en marcha rápidamente con una inversión mínima en servicios de infraestructura. Nuevas características se entregan automáticamente, lo que le ahorra un mantenimiento continuado y costos de actualización.

Con la solución de contenedor de Operations Management Suite, puede hacer lo siguiente:

-   Centralizar y correlacionar millones de registros de contenedores de Docker a escala

-   Ver información sobre todos los hosts de contenedor en una sola ubicación

-   Saber qué contenedores están ejecutando, qué imagen se están ejecutando y donde se están ejecutando

-   Diagnosticar rápidamente los contenedores de "vecino ruidoso" que pueden causar problemas en los hosts de contenedor

-   Vea una pista de auditoría para las acciones sobre contenedores

-   Solucionar errores viendo y buscar registros centralizados sin comunicación remota a los hosts de Docker

-   Encontrar los contenedores que podrían ser "vecinos ruidosos" y el consumo excesivo de recursos en un host

-   Ver información de uso y el rendimiento de red de contenedores, memoria, almacenamiento y centralizada CPU

-   Generar prueba contenedores de Docker con Azure Automation

Puede ver información sobre el rendimiento mediante la ejecución de consultas, como el tipo = Perf, tal como se muestra en la figura 6-3.

![DockerPerfMetricsView](./media/image3.png){width = "5.78625 en" height = "3,25 en"}

Figura 6-3: las métricas de rendimiento de hosts de Docker que se muestra por Operations Management Suite

Guardar las consultas también es una característica estándar en Operations Management Suite y puede ayudarle a mantener las consultas que haya encontrado más útiles y detectar tendencias en el sistema.

**Obtener más información** para encontrar información sobre cómo instalar y configurar el Docker de solución de contenedor en [Operations Management Suite](https://microsoft.com/oms), vaya a <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.

>[!div class="step-by-step"]
[Anterior](manage-production-docker-environments.md)
[Siguiente](../key-takeaways/index.md)

---
title: "Modernizar las aplicaciones con la supervisión y telemetría"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Modernizar las aplicaciones con la supervisión y telemetría"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 03a6f2be9dc6c020cfe93a2597d1288943e527c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernizar las aplicaciones con la supervisión y telemetría

Al ejecutar una aplicación en producción, es fundamental que tiene información sobre el rendimiento de la aplicación. ¿Realiza en un nivel alto? ¿Los usuarios reciben errores o es la aplicación estable y confiable? Debe enriquecido supervisión de rendimiento, eficaces de alertas y paneles para ayudar a garantizar que la aplicación esté disponible y rendimiento según lo previsto. También debe ser capaz de ver rápidamente si hay un problema, determine cuántos clientes se ven afectados y realizan un análisis de causa raíz para buscar y corregir el problema.

## <a name="monitor-your-application-with-application-insights"></a>Supervisar la aplicación con Application Insights

Visión de la aplicación es un servicio de administración de rendimiento de aplicaciones (APM) extensible para los desarrolladores web que trabajan en varias plataformas. Usar para supervisar la aplicación web en vivo. Visión de la aplicación detecta automáticamente las anomalías de rendimiento. Incluye herramientas de análisis eficaces para ayudar a diagnosticar problemas y para ayudarle a comprender lo que los usuarios hacer con la aplicación. Visión de la aplicación está diseñada para ayudarle a mejorar continuamente el rendimiento y facilidad de uso. Funciona para las aplicaciones en una amplia variedad de plataformas, como. NET, Node.js y J2EE, si hospedado en local o en la nube. Visión de la aplicación se integra con los procesos de DevOps y tiene puntos de conexión a una variedad de herramientas de desarrollo.

Figura 4-10 se muestra un ejemplo de cómo Application Insights supervisa su aplicación y cómo presenta esta información a un panel.

![Panel de supervisión de Application Insights](./media/image10.png)

> **Figura 4-10.** Panel de supervisión de Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Supervisar la infraestructura de Docker con análisis de registros y su solución de supervisión de contenedor

[Análisis de registros de Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) forma parte de la [general de solución de supervisión de Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). También es un servicio [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Análisis de registros supervisa en la nube y en entornos locales (OMS local) para ayudar a mantener la disponibilidad y rendimiento. Recopila los datos generados por los recursos en los entornos de nube y locales y de otras herramientas de supervisión para proporcionar análisis a través de varios orígenes.

En relación con los registros de infraestructura de Azure, análisis de registros, como un servicio de Azure, recopila datos de registro y la métrica de otros servicios de Azure (a través de [Monitor Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), máquinas virtuales de Azure, contenedores de Docker y otras infraestructuras de nube o local. Análisis de registros ofrecen búsqueda de registros flexible y análisis de fuera del cuadro encima de estos datos. Proporciona herramientas enriquecidas que puede utilizar para analizar los datos en orígenes, permite las consultas más complejas en todos los registros, y se puede alertar de manera proactiva en función de las condiciones especificadas. Incluso puede recopilar datos personalizados en el repositorio de análisis de registro central, donde puede consultar y visualizarla. También pueden aprovechar de las soluciones integradas de análisis de registros para obtener información sobre la seguridad de forma inmediata y la funcionalidad de la infraestructura.

Puede tener acceso a análisis de registros en el portal OMS o el portal de Azure, que se ejecutan en cualquier explorador, y proporcionar acceso a valores de configuración y varias herramientas para analizar y actuar sobre los datos recopilados.

El [solución de supervisión de contenedor](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) en análisis de registros le ayuda a ver y administrar los hosts de Docker y el contenedor de Windows en una sola ubicación. La solución muestra qué contenedores están ejecutando, qué imagen de contenedor se está ejecutando y que se ejecutan los contenedores. Puede ver información detallada de auditoría, incluidos los comandos que se utilizan con los contenedores. También puede solucionar los contenedores de visualización y búsqueda de registros centralizados, sin necesidad de ver de forma remota los hosts de Windows o de Docker. Puede encontrar contenedores que podrían ser ruidoso y consumo exceso de recursos en un host. Además, puede ver centralizada CPU, memoria, almacenamiento y uso de la red y obtener información de rendimiento, para los contenedores. En equipos que ejecutan Windows, puede centralizar y comparar los registros de Windows Server, Hyper-V y contenedores de Docker. La solución es compatible con la siguiente orchestrators de contenedor:

-   Conjunto de docker

-   CONTROLADOR DE DOMINIO/OS

-   Kubernetes

-   Service Fabric.

-   Red Hat OpenShift

Figura 4-11 muestra las relaciones entre varios hosts de contenedor y los agentes y OMS.

![Solución de supervisión de contenedor de análisis de registro](./media/image11.png)

> **Figura 4-11.** Solución de supervisión de contenedor de análisis de registro

Puede usar la solución de supervisión de contenedor de análisis de registro:

-   Ver información sobre todos los hosts de contenedor en una sola ubicación.

-   Saber qué contenedores están ejecutando, la imagen que se ejecutan y donde se está ejecutando.

-   Vea una pista de auditoría de acciones en los contenedores.

-   Solucionar problemas mediante la visualización y búsqueda de registros centralizados sin inicio de sesión remoto a los hosts de Docker.

-   Buscar contenedores que podrían ser "vecino ruidoso" y estar consumiendo exceso de recursos en un host.

-   Ver centralizada CPU, memoria, almacenamiento y uso de la red y obtener información de rendimiento, para los contenedores.

### <a name="additional-resources"></a>Recursos adicionales

-   **Información general de supervisión de Microsoft Azure**

[https://docs.Microsoft.com/Azure/Monitoring-and-Diagnostics/Monitoring-Overview](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   **¿Qué es Application Insights?**

[https://docs.Microsoft.com/Azure/Application-Insights/App-Insights-Overview](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   **¿Qué es el análisis de registros?**

[https://docs.Microsoft.com/Azure/log-Analytics/log-Analytics-Overview](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   **Solución de supervisión de contenedor en el análisis de registros**

[https://docs.Microsoft.com/Azure/log-Analytics/log-Analytics-Containers](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   **Información general del Monitor de Azure**

[https://docs.Microsoft.com/Azure/Monitoring-and-Diagnostics/Monitoring-Overview-Azure-Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   **¿Qué es Operations Management Suite (OMS)?**

[https://docs.Microsoft.com/Azure/Operations-Management-Suite/Operations-Management-Suite-Overview](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   **Supervisión de contenedores de Windows Server en Service Fabric con OMS**

[https://docs.Microsoft.com/Azure/Service-fabric/Service-fabric-Diagnostics-Containers-WindowsServer](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
[Anterior](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Siguiente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)

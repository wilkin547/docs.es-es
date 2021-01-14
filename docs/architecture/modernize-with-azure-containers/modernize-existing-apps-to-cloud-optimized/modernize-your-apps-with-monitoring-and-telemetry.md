---
title: Modernización de aplicaciones con supervisión y telemetría
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Modernice sus aplicaciones con supervisión y telemetría
ms.date: 12/21/2020
ms.openlocfilehash: c79a16400ce9dadca50fabb6c7df2859e4519a41
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025243"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernización de aplicaciones con supervisión y telemetría

Al ejecutar una aplicación en producción, es fundamental que tenga información sobre el rendimiento de la aplicación. ¿Está funcionando a un alto nivel? ¿Los usuarios tienen errores o la aplicación es estable y confiable? Necesita una amplia supervisión del rendimiento, alertas eficaces y paneles que le ayudarán a garantizar que la aplicación esté disponible y funcione según lo previsto. También debe poder ver rápidamente si hay un problema, determinar cuántos clientes se ven afectados y realizar un análisis de la causa principal para buscar y corregir el problema.

## <a name="monitor-your-application-with-application-insights"></a>Supervisión de la aplicación con Application Insights

Azure Application Insights es un servicio de Application Performance Management (APM) extensible para desarrolladores web que trabajan en varias plataformas. Úselo para supervisar la aplicación web en directo. Application Insights detecta automáticamente anomalías en el rendimiento. Incluye herramientas de análisis eficaces que le ayudan a diagnosticar problemas y comprender lo que hacen realmente los usuarios con la aplicación. Application Insights está diseñado para ayudarle a mejorar continuamente el rendimiento y la facilidad de uso. Funciona con diversas aplicaciones y en una amplia variedad de plataformas, como .NET, Node.js o J2EE, tanto hospedadas localmente como en la nube. Application Insights se integra con los procesos de DevOps y tiene puntos de conexión a diversas herramientas de desarrollo.

En la figura 4-10 se muestra un ejemplo de cómo Application Insights supervisa la aplicación y cómo expone esa información en un panel.

![Captura de pantalla del panel de supervisión de Application Insights.](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

**Figura 4-10.** Panel de supervisión de Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Supervisión de la infraestructura de Docker con Log Analytics y su solución de supervisión de contenedores

[Azure Log Analytics](/azure/log-analytics/log-analytics-overview) forma parte de la [solución de supervisión global de Microsoft Azure](/azure/monitoring-and-diagnostics/monitoring-overview). También es un servicio de [Operations Management Suite (OMS)](/azure/operations-management-suite/operations-management-suite-overview). Log Analytics supervisa los entornos locales y en la nube (OMS para el entorno local) para ayudar a mantener la disponibilidad y el rendimiento. Recopila los datos generados por los recursos en los entornos local y de nube y mediante otras herramientas de supervisión, para proporcionar análisis entre varios orígenes.

En cuanto a los registros de infraestructura de Azure, Log Analytics, como servicio de Azure, ingiere los datos de registro y métricas de otros servicios de Azure (mediante [Azure Monitor](/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), máquinas virtuales de Azure, contenedores de Docker y otras infraestructuras en la nube o locales. Log Analytics ofrece una búsqueda de registros flexible y análisis predefinidos para estos datos. Proporciona herramientas enriquecidas que puede usar para analizar los datos de diversos orígenes, permite consultas complejas en todos los registros y puede generar alertas activas según las condiciones especificadas. Incluso puede recopilar datos personalizados en el repositorio central de Log Analytics, donde puede consultarlos y visualizarlos. También puede aprovechar las soluciones integradas de Log Analytics para obtener conclusiones de forma inmediata sobre la seguridad y la funcionalidad de la infraestructura.

Puede acceder a Log Analytics a través del portal de OMS o de Azure Portal, que se ejecuta en cualquier explorador, y le proporciona acceso a las opciones de configuración y a varias herramientas para analizar y realizar acciones sobre los datos recopilados.

La [solución de supervisión de contenedores](/azure/log-analytics/log-analytics-containers) de Log Analytics le ayuda a ver y administrar los hosts de contenedores de Docker y Windows en una sola ubicación. La solución muestra qué contenedores están en ejecución, qué imagen de contenedor están ejecutando y dónde se ejecutan los contenedores. Puede ver información detallada de auditoría, incluidos los comandos que se usan con los contenedores. También puede solucionar problemas de los contenedores si examina y busca registros centralizados, sin tener que ver los hosts de Docker o Windows de forma remota. Puede encontrar los contenedores que están causando ruido o realizando un consumo excesivo de recursos en un host. También puede ver la información centralizada acerca de la CPU, la memoria, el almacenamiento y el uso y el rendimiento de la red en relación con los contenedores. En equipos con Windows, puede centralizar y comparar registros de Windows Server, Hyper-V y contenedores de Docker. La solución es compatible con los siguientes orquestadores de contenedores:

- Docker Swarm

- DC/OS

- Kubernetes

- Red Hat OpenShift

La figura 4-11 muestra las relaciones entre varios hosts de contenedores y los agentes con OMS.

![Captura de pantalla de la solución de supervisión de contenedores de Log Analytics.](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

**Figura 4-11.** Solución de Supervisión de contenedores de Log Analytics

Puede usar la solución de supervisión de contenedores de Log Analytics para:

- Ver la información de todos los hosts de contenedor en una sola ubicación.

- Saber qué contenedores se están ejecutando, qué imagen están ejecutando y dónde se ejecutan.

- Ver una traza de auditoría de las acciones en los contenedores.

- Solucionar problemas mediante la consulta y búsqueda de registros centralizados sin iniciar sesión remota en los hosts de Docker.

- Encontrar los contenedores que están causando ruido o realizando un consumo excesivo de recursos en un host.

- Ver la información centralizada acerca de la CPU, la memoria, el almacenamiento, y el uso y el rendimiento de la red en relación con los contenedores.

### <a name="additional-resources"></a>Recursos adicionales

- **Información general sobre la supervisión en Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Application Insights?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **¿Qué es Log Analytics?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Solución de supervisión de contenedores de Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Información general sobre Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Operations Management Suite (OMS)?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[Anterior](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Siguiente](life-cycle-ci-cd-pipelines-devops-tools.md)

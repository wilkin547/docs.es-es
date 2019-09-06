---
title: Modernización de aplicaciones con supervisión y telemetría
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Modernice sus aplicaciones con supervisión y telemetría
ms.date: 04/30/2018
ms.openlocfilehash: 65c464e27e326f6a60b4879ec787253dea019d92
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373950"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernización de aplicaciones con supervisión y telemetría

Al ejecutar una aplicación en producción, es fundamental que tenga información sobre el rendimiento de la aplicación. ¿Está funcionando a un alto nivel? ¿Los usuarios obtienen errores o la aplicación es estable y confiable? Necesita una amplia supervisión del rendimiento, alertas eficaces y paneles para ayudar a garantizar que la aplicación esté disponible y funcione según lo previsto. También debe poder ver rápidamente si hay un problema, determinar cuántos clientes se ven afectados y realizar un análisis de la causa principal para buscar y corregir el problema.

## <a name="monitor-your-application-with-application-insights"></a>Supervisar la aplicación con Application Insights

Application Insights es un servicio de administración de rendimiento de aplicaciones (APM) extensible para desarrolladores web que trabajan en varias plataformas. Úselo para supervisar la aplicación web en directo. Application Insights detecta automáticamente las anomalías de rendimiento. Incluye eficaces herramientas de análisis para ayudarle a diagnosticar problemas y ayudarle a comprender qué hacen realmente los usuarios con la aplicación. Application Insights está diseñado para ayudarle a mejorar continuamente el rendimiento y la facilidad de uso. Funciona para aplicaciones en una amplia variedad de plataformas, como .NET, node. js y J2EE, tanto si están hospedadas en el entorno local como en la nube. Application Insights se integra con los procesos de DevOps y tiene puntos de conexión a diversas herramientas de desarrollo.

En la figura 4-10 se muestra un ejemplo de cómo Application Insights supervisa la aplicación y cómo se expone esa información a un panel.

![Panel de supervisión de Application Insights](./media/image10.png)

**Figura 4-10.** Panel de supervisión de Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Supervise la infraestructura de Docker con Log Analytics y su solución de supervisión de contenedores

[Azure log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) forma parte de la [solución de supervisión general Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). También es un servicio de [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analytics supervisa los entornos locales y en la nube (OMS para el entorno local) para ayudar a mantener la disponibilidad y el rendimiento. Recopila los datos generados por los recursos en los entornos local y de nube y mediante otras herramientas de supervisión, para proporcionar análisis entre varios orígenes.

En relación con los registros de infraestructura de Azure, Log Analytics, como un servicio de Azure, introduce datos de registro y métricas de otros servicios de Azure (a través de [Azure monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), máquinas virtuales de Azure, contenedores de Docker y otras infraestructuras en la nube o locales. Log Analytics ofrece una búsqueda de registros flexible y análisis no integrados sobre estos datos. Proporciona herramientas enriquecidas que puede usar para analizar datos entre orígenes, permite consultas complejas en todos los registros y puede generar alertas proactivas según las condiciones especificadas. Incluso puede recopilar datos personalizados en el repositorio central de Log Analytics, donde puede consultarlos y visualizarlos. También puede aprovechar las soluciones integradas de Log Analytics para obtener información de forma inmediata sobre la seguridad y la funcionalidad de la infraestructura.

Puede tener acceso a Log Analytics a través del portal de OMS o del Azure Portal, que se ejecutan en cualquier explorador, y le proporcionan acceso a las opciones de configuración y a varias herramientas para analizar y actuar en los datos recopilados.

La [solución de supervisión de contenedores](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) de log Analytics le ayuda a ver y administrar los hosts de contenedor de Docker y Windows en una sola ubicación. La solución muestra qué contenedores se están ejecutando, qué imagen de contenedor se ejecutan y dónde se ejecutan los contenedores. Puede ver información detallada de auditoría, incluidos los comandos que se usan con contenedores. También puede solucionar problemas de contenedores viendo y buscando registros centralizados sin necesidad de ver de forma remota los hosts de Docker o Windows. Puede encontrar contenedores que podrían ser ruidosos y consumir exceso de recursos en un host. Además, puede ver la CPU centralizada, la memoria, el almacenamiento y el uso de la red, así como la información de rendimiento, para contenedores. En equipos con Windows, puede centralizar y comparar registros de Windows Server, Hyper-V y contenedores de Docker. La solución es compatible con los siguientes orquestadores de contenedores:

- Docker Swarm

- DC/OS

- kubernetes

- Red Hat OpenShift

En la figura 4-11 se muestran las relaciones entre varios hosts de contenedor y agentes y OMS.

![Log Analytics solución de supervisión de contenedores](./media/image11.png)

**Figura 4-11.** Log Analytics solución de supervisión de contenedores

Puede usar la solución de supervisión de contenedores Log Analytics para:

- Vea la información sobre todos los hosts de contenedor en una sola ubicación.

- Sepa qué contenedores se están ejecutando, qué imagen están ejecutando y dónde se ejecutan.

- Vea una traza de auditoría para ver las acciones de los contenedores.

- Para solucionar problemas, consulte y busque registros centralizados sin inicio de sesión remoto en los hosts de Docker.

- Busque contenedores que podrían ser "vecinos ruidosos" y consumen exceso de recursos en un host.

- Ver la CPU centralizada, la memoria, el almacenamiento y el uso de la red, así como la información de rendimiento, para contenedores.

### <a name="additional-resources"></a>Recursos adicionales

- **Información general sobre la supervisión en Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Application Insights?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **¿Qué es Log Analytics?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Solución de supervisión de contenedores en Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Información general de Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Operations Management Suite (OMS)?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[Anterior](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Siguiente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)

---
title: Modernización de aplicaciones con supervisión y telemetría
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Modernice sus aplicaciones con supervisión y telemetría
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: a8135031d2879ff377881d246c532573a2149fe7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611654"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>Modernización de aplicaciones con supervisión y telemetría

Al ejecutar una aplicación en producción, es fundamental que dispone de información detallada sobre el rendimiento de la aplicación. ¿Se ejecuta en un nivel alto? ¿Los usuarios reciben errores o es la aplicación estable y confiable? Se necesitan la supervisión de alto rendimiento, alertas y muy eficaces, paneles para ayudar a garantizar que la aplicación está disponible y funciona según lo previsto. También deberá ser capaz de ver rápidamente si hay un problema, determine cuántos clientes se ven afectados y realizan un análisis de causa raíz para buscar y corregir el problema.

## <a name="monitor-your-application-with-application-insights"></a>Supervisar la aplicación con Application Insights

Application Insights es un servicio de Application Performance Management (APM) extensible para desarrolladores web que trabajan en varias plataformas. Usarlo para supervisar la aplicación web activa. Application Insights detecta automáticamente las anomalías de rendimiento. Incluye herramientas de análisis eficaces que le ayudarán a diagnosticar problemas y que le ayudarán a comprender lo que los usuarios hacen con su aplicación. Application Insights está diseñado para ayudarle a mejorar continuamente el rendimiento y facilidad de uso. Funciona para las aplicaciones en una amplia variedad de plataformas, incluidas. NET, Node.js y J2EE, ya sean hospedados localmente o en la nube. Application Insights se integra con los procesos de DevOps y tiene puntos de conexión a una variedad de herramientas de desarrollo.

Figura 4-10 se muestra un ejemplo de cómo Application Insights supervisa la aplicación y cómo presenta esa información a un panel.

![Panel de supervisión de Application Insights](./media/image10.png)

> **Figura 4-10.** Panel de supervisión de Application Insights

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>Supervisar la infraestructura de Docker con Log Analytics y su solución de supervisión de contenedores

[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) forma parte de la [general de solución de supervisión de Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview). También es un servicio en [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview). Log Analytics supervisa en la nube y entornos locales (OMS para un entorno local) para ayudar a mantener la disponibilidad y rendimiento. Recopila los datos generados por los recursos en sus entornos de nube y locales y desde otras herramientas de supervisión para proporcionar análisis entre varios orígenes.

En relación con los registros de infraestructura de Azure Log Analytics, como un servicio de Azure ingiere datos de registro y métricas de otros servicios de Azure (a través de [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), máquinas virtuales de Azure, contenedores de Docker y en el entorno local u otras infraestructuras de nube. Log Analytics ofrece búsqueda de registros flexible y análisis de fuera del cuadro en estos datos. Proporciona herramientas enriquecidas que puede usar para analizar datos en orígenes, permite realizar consultas complejas en todos los registros y puede alertar de forma proactiva según las condiciones especificadas. Incluso puede recopilar datos personalizados en el repositorio central de Log Analytics, donde puede consultarlos y visualizarlos. También puede aprovechar las ventajas de las soluciones integradas de Log Analytics para obtener información sobre la seguridad de forma inmediata y la funcionalidad de la infraestructura.

Puede acceder a Log Analytics a través del portal de OMS o Azure portal, que se ejecutan en cualquier explorador, y proporcionar acceso a los valores de configuración y a varias herramientas para analizar y actuar sobre los datos recopilados.

El [solución de supervisión de contenedores](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) en Log Analytics le ayuda a ver y administrar los hosts de Docker y el contenedor de Windows en una sola ubicación. La solución muestra qué contenedores están ejecutando, qué imagen de contenedor se están ejecutando y que se ejecutan los contenedores. Puede ver información detallada de auditoría, incluidos los comandos que se usan con contenedores. También puede solucionar los contenedores de ver y buscar registros centralizados, sin necesidad de ver los hosts de Docker o Windows de forma remota. Puede encontrar los contenedores que podrían ser ruidoso y consumo excesivo de recursos en un host. Además, puede ver centralizada CPU, memoria, almacenamiento y uso de la red y la información de rendimiento, para los contenedores. En equipos que ejecutan Windows, puede centralizar y comparar registros de Windows Server, Hyper-V y contenedores de Docker. La solución admite los siguientes orquestadores de contenedor:

- Docker Swarm

- DC/OS

- Kubernetes

- Service Fabric

- Red Hat OpenShift

Figura 4-11 muestra las relaciones entre varios hosts de contenedores y los agentes y OMS.

![Solución de supervisión de contenedores de análisis de registro](./media/image11.png)

> **Figura 4-11.** Solución de supervisión de contenedores de análisis de registro

Puede usar la solución de supervisión de contenedores de Log Analytics para:

- Ver información sobre todos los hosts de contenedor en una sola ubicación.

- Saber qué contenedores están ejecutando, qué imagen se están ejecutando y donde se están ejecutando.

- Vea una pista de auditoría para las acciones en contenedores.

- Solucionar errores viendo y buscar registros centralizados sin inicio de sesión remoto a los hosts de Docker.

- Buscar contenedores que podrían ser "vecinos ruidosos" y se consumo excesivo de recursos en un host.

- Ver centralizada CPU, memoria, almacenamiento y uso de la red y la información de rendimiento, para los contenedores.

### <a name="additional-resources"></a>Recursos adicionales

- **Información general de supervisión en Microsoft Azure**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Application Insights?**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **¿Qué es Log Analytics?**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Solución de supervisión de contenedores en Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Información general sobre Azure Monitor**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Operations Management Suite (OMS)?**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

- **Supervisión de contenedores de Windows Server en Service Fabric con OMS**

<https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver>

>[!div class="step-by-step"]
>[Anterior](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Siguiente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)

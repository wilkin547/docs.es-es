---
title: Supervisar los servicios de aplicación en contenedor
description: Obtenga información sobre algunos aspectos clave de supervisión de las arquitecturas de contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 925db543617deb28590cf6631ebbda3ee96836c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975750"
---
# <a name="monitor-containerized-application-services"></a>Supervisar los servicios de aplicación en contenedor

Es fundamental para las aplicaciones que se divide en varios contenedores y microservicios tiene una forma de supervisar y analizar el comportamiento de toda la aplicación.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) es un servicio de análisis extensible que supervisa la aplicación activa. Le ayuda a detectar y diagnosticar problemas de rendimiento y comprender lo que los usuarios hacen con su aplicación. Está diseñado para desarrolladores, con la intención de ayudarle a mejorar continuamente el rendimiento y facilidad de uso de los servicios o aplicaciones. Application Insights funciona con/servicios web e independiente de aplicaciones en una amplia variedad de plataformas como. NET, Java, Node.js y muchas otras plataformas, hospedadas en local o en la nube.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Análisis de aplicaciones de Docker en entornos de preguntas y respuestas con Application Insights

Lo que respecta a Docker, podrá crear un gráfico eventos de ciclo de vida y los contadores de rendimiento de los contenedores de Docker en Application Insights. Deberá ejecutar el [imagen de Docker de Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) como un contenedor en el host y se mostrarán los contadores de rendimiento para el host, así como para las demás imágenes de Docker. Esta imagen de Docker de Application Insights (figura 6 - 1) le ayuda a supervisar sus aplicaciones de contenedor mediante la recopilación de datos de telemetría sobre el rendimiento y la actividad de su host de Docker (es decir, las máquinas virtuales de Linux), los contenedores de Docker y las aplicaciones que se ejecutan dentro de ellos.

![ejemplo](./media/image1.png)

**Figura 6-1**. Supervisión de contenedores y los hosts de Docker de Application Insights

Al ejecutar el [imagen de Docker de Application Insights](https://hub.docker.com/r/microsoft/applicationinsights/) en el host de Docker, beneficiarse de las siguientes:

- Datos de telemetría sobre todos los contenedores que se ejecutan en el host de ciclo de vida, iniciar, detener y así sucesivamente.

- Contadores de rendimiento para todos los contenedores: CPU, memoria, uso de la red y mucho más.

- Si también ha instalado [SDK de Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) en las aplicaciones que se ejecutan en los contenedores, toda la telemetría de dichas aplicaciones tendrán propiedades adicionales que identifiquen el contenedor y el equipo host. Por lo tanto, por ejemplo, si tiene instancias de una aplicación que se ejecuta en más de un host, fácilmente podrá filtrar los datos de telemetría de aplicación por host.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>Configuración de Application Insights para supervisar aplicaciones de Docker y los hosts de Docker

Para crear un recurso de Application Insights, siga las instrucciones en los artículos que se presentan en la lista siguiente. Portal de Azure creará el script necesario para usted.

- **Supervisar aplicaciones Docker en Application Insights:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-docker>

- **Imagen de Docker de la información de la aplicación en Docker Hub y GitHub:** \
  <https://hub.docker.com/r/microsoft/applicationinsights/> y \
  <https://github.com/Microsoft/ApplicationInsights-Docker>

- **Configurar Application Insights para aplicaciones web ASP.NET y ASP.NET Core:** \
  <https://docs.microsoft.com/azure/application-insights/app-insights-asp-net>

- **Application Insights para páginas web:**  
  <https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="security-backup-and-monitoring-services"></a>Seguridad, copia de seguridad y supervisión de servicios

Hay muchas tareas de soporte técnico con una gran cantidad de detalles que se deben controlar para garantizar que sus aplicaciones e infraestructura están en estado de la ranura superior para admitir las necesidades empresariales y la situación se vuelve más complicada en el dominio Kerberos de microservicios, por lo que necesita una manera de tiene vistas detalladas y de alto nivel cuando deba tomar medidas.

Azure tiene las herramientas para administrar y proporcionar una vista unificada de cuatro aspectos críticos de recursos de la nube y el local:

- **Seguridad**. Con [Azure Security Center](https://azure.microsoft.com/services/security-center/).
  - Obtenga total visibilidad y control sobre la seguridad de sus máquinas virtuales, aplicaciones y cargas de trabajo.
  - Centralizar la administración de las directivas de seguridad e integrar herramientas y procesos existentes.
  - Detectar amenazas reales con análisis avanzado.

- **Copia de seguridad**. Con [copia de seguridad de Azure](https://azure.microsoft.com/services/backup/).
  - Evitar interrupciones empresariales costosas, cumplir los objetivos de cumplimiento normativo y proteja sus datos frente a ransomware y errores humanos.
  - Mantener los datos de copia de seguridad cifrados en tránsito y en reposo.
  - Asegúrese de acceso basado en la autenticación multifactor para evitar el uso no autorizado.

- **Supervisión**. Con [supervisión de Azure](https://azure.microsoft.com/solutions/monitoring/), [Log Analytics](https://azure.microsoft.com/services/log-analytics/), y [Application Insights](https://azure.microsoft.com/services/application-insights/).
  - Obtenga visibilidad total del estado y rendimiento de sus cargas de trabajo de Azure, aplicaciones e infraestructura.
  - Recopilar datos de cualquier origen y obtener información valiosa en sus máquinas virtuales, contenedores y aplicaciones.
  - Encuentre la información que necesita el uso de consultas interactivas y búsqueda de texto completo. 
  - Realizar análisis de causa raíz con análisis avanzado, incluidos los algoritmos de aprendizaje automático.

- **Los recursos locales**. Con [una nube híbrida verdaderamente coherente](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Anterior](manage-production-docker-environments.md)
>[Siguiente](../key-takeaways/index.md)

---
title: Supervisión de servicios de aplicaciones en contenedor
description: Obtenga información sobre algunos aspectos clave de supervisión de las arquitecturas de contenedor
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641223"
---
# <a name="monitor-containerized-application-services"></a>Supervisión de servicios de aplicaciones en contenedor

Es fundamental para las aplicaciones que se divide en varios contenedores y microservicios tiene una forma de supervisar y analizar el comportamiento de toda la aplicación.

## <a name="azure-monitor"></a>Azure Monitor

[Azure Monitor](https://azure.microsoft.com/services/monitor/) es un servicio de análisis extensible que supervisa la aplicación activa. Le ayuda a detectar y diagnosticar problemas de rendimiento y comprender lo que los usuarios hacen con su aplicación. Está diseñado para desarrolladores, con la intención de ayudarle a mejorar continuamente el rendimiento y facilidad de uso de los servicios o aplicaciones. Azure Monitor funciona con/servicios web e independiente aplicaciones en una amplia variedad de plataformas como. NET, Java, Node.js y muchas otras plataformas, hospedadas en local o en la nube.

### <a name="additional-resources"></a>Recursos adicionales

- **Información general sobre Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Application Insights?** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **¿Qué es la supervisión de las métricas de Azure?** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Solución de supervisión de contenedores en Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>Servicios de seguridad y copia de seguridad

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

- **Los recursos locales**. Con [una nube híbrida verdaderamente coherente](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Anterior](manage-production-docker-environments.md)
>[Siguiente](../key-takeaways/index.md)

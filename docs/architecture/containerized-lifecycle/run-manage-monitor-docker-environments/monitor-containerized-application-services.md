---
title: Supervisión de servicios de aplicaciones en contenedor
description: Conozca algunos aspectos clave de la supervisión de arquitecturas de contenedor
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673462"
---
# <a name="monitor-containerized-application-services"></a>Supervisión de servicios de aplicaciones en contenedor

Es fundamental que las aplicaciones que se dividen en varios contenedores y microservicios cuenten con una forma de supervisar y analizar el comportamiento de toda la aplicación.

## <a name="azure-monitor"></a>Azure Monitor

[Azure Monitor](https://azure.microsoft.com/services/monitor/) es un servicio de análisis extensible que supervisa su aplicación activa. Le ayuda a detectar y diagnosticar problemas de rendimiento y a comprender qué hacen los usuarios realmente con su aplicación. Está diseñado para desarrolladores, con la intención de ayudarle a mejorar continuamente el rendimiento y la facilidad de uso de sus servicios o aplicaciones. Azure Monitor trabaja tanto con web/servicios como con aplicaciones independientes en una amplia variedad de plataformas como.NET, Java, Node.js y muchas otras, hospedadas en local o en la nube.

### <a name="additional-resources"></a>Recursos adicionales

- **Información general sobre Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **¿Qué es Application Insights?** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **¿Qué es el Explorador de métricas de Azure Monitor?** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Solución de supervisión de contenedores de Azure Monitor** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>Servicios de seguridad y copia de seguridad

Hay muchas tareas de soporte técnico con muchos detalles que hay que controlar para garantizar que las aplicaciones y la infraestructura estén en condiciones óptimas para satisfacer las necesidades de la empresa. Esta situación se complica en el ámbito de los microservicios, por lo que ha de tener vistas generales y detalladas cuando tenga que tomar medidas.

Azure cuenta con las herramientas necesarias para administrar y proporcionar una vista unificada de cuatro aspectos críticos tanto de los recursos en la nube como en local:

- **Seguridad**. Con [Azure Security Center](https://azure.microsoft.com/services/security-center/).
  - Obtenga total visibilidad y control sobre la seguridad de sus máquinas virtuales, aplicaciones y cargas de trabajo.
  - Centralice la administración de las directivas de seguridad e integre herramientas y procesos existentes.
  - Detecte amenazas reales con análisis avanzado.

- **Copia de seguridad**. Con [Azure Backup](https://azure.microsoft.com/services/backup/).
  - Evite costosas interrupciones de actividad de la empresa, cumpla los objetivos de cumplimiento normativo y proteja sus datos frente a ransomware y errores humanos.
  - Mantenga los datos de copia de seguridad cifrados en tránsito y en reposo.
  - Garantice el acceso basado en la autenticación multifactor para evitar el uso no autorizado.

- **Recursos locales**. Con [una nube híbrida realmente confiable](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).

>[!div class="step-by-step"]
>[Anterior](manage-production-docker-environments.md)
>[Siguiente](../key-takeaways/index.md)

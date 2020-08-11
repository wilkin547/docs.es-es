---
title: Supervisión de servicios de aplicaciones en contenedor
description: Conozca algunos aspectos clave de la supervisión de arquitecturas de contenedor
ms.date: 08/06/2020
ms.openlocfilehash: 5fcb5065d02018ab3c2d3ad71cf507bd43b53446
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87914939"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="1597c-103">Supervisión de servicios de aplicaciones en contenedor</span><span class="sxs-lookup"><span data-stu-id="1597c-103">Monitor containerized application services</span></span>

<span data-ttu-id="1597c-104">Es fundamental que las aplicaciones que se dividen en varios contenedores y microservicios cuenten con una forma de supervisar y analizar el comportamiento de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1597c-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="1597c-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="1597c-105">Azure Monitor</span></span>

<span data-ttu-id="1597c-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) es un servicio de análisis extensible que supervisa su aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="1597c-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="1597c-107">Le ayuda a detectar y diagnosticar problemas de rendimiento y a comprender qué hacen los usuarios realmente con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="1597c-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="1597c-108">Está diseñado para desarrolladores, con la intención de ayudarle a mejorar continuamente el rendimiento y la facilidad de uso de sus servicios o aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1597c-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="1597c-109">Azure Monitor trabaja tanto con web/servicios como con aplicaciones independientes en una amplia variedad de plataformas como.NET, Java, Node.js y muchas otras, hospedadas en local o en la nube.</span><span class="sxs-lookup"><span data-stu-id="1597c-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1597c-110">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1597c-110">Additional resources</span></span>

- <span data-ttu-id="1597c-111">**Información general sobre Azure Monitor** </span><span class="sxs-lookup"><span data-stu-id="1597c-111">**Overview of Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="1597c-112">**¿Qué es Application Insights?**</span><span class="sxs-lookup"><span data-stu-id="1597c-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="1597c-113">**¿Qué es el Explorador de métricas de Azure Monitor?**</span><span class="sxs-lookup"><span data-stu-id="1597c-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="1597c-114">**Solución de supervisión de contenedores de Azure Monitor** </span><span class="sxs-lookup"><span data-stu-id="1597c-114">**Container Monitoring solution in Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="1597c-115">Servicios de seguridad y copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="1597c-115">Security and backup services</span></span>

<span data-ttu-id="1597c-116">Hay muchas tareas de soporte técnico con muchos detalles que hay que controlar para garantizar que las aplicaciones y la infraestructura estén en condiciones óptimas para satisfacer las necesidades de la empresa. Esta situación se complica en el ámbito de los microservicios, por lo que ha de tener vistas generales y detalladas cuando tenga que tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="1597c-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="1597c-117">Azure cuenta con las herramientas necesarias para administrar y proporcionar una vista unificada de cuatro aspectos críticos tanto de los recursos en la nube como en local:</span><span class="sxs-lookup"><span data-stu-id="1597c-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="1597c-118">**Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="1597c-118">**Security**.</span></span> <span data-ttu-id="1597c-119">Con [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span><span class="sxs-lookup"><span data-stu-id="1597c-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="1597c-120">Obtenga total visibilidad y control sobre la seguridad de sus máquinas virtuales, aplicaciones y cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1597c-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="1597c-121">Centralice la administración de las directivas de seguridad e integre herramientas y procesos existentes.</span><span class="sxs-lookup"><span data-stu-id="1597c-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="1597c-122">Detecte amenazas reales con análisis avanzado.</span><span class="sxs-lookup"><span data-stu-id="1597c-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="1597c-123">**Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="1597c-123">**Backup**.</span></span> <span data-ttu-id="1597c-124">Con [Azure Backup](https://azure.microsoft.com/services/backup/).</span><span class="sxs-lookup"><span data-stu-id="1597c-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="1597c-125">Evite costosas interrupciones de actividad de la empresa, cumpla los objetivos de cumplimiento normativo y proteja sus datos frente a ransomware y errores humanos.</span><span class="sxs-lookup"><span data-stu-id="1597c-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="1597c-126">Mantenga los datos de copia de seguridad cifrados en tránsito y en reposo.</span><span class="sxs-lookup"><span data-stu-id="1597c-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="1597c-127">Garantice el acceso basado en la autenticación multifactor para evitar el uso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="1597c-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="1597c-128">**Recursos locales**.</span><span class="sxs-lookup"><span data-stu-id="1597c-128">**On-premises resources**.</span></span> <span data-ttu-id="1597c-129">Con [soluciones de nube híbrida](https://azure.microsoft.com/solutions/hybrid-cloud-app/).</span><span class="sxs-lookup"><span data-stu-id="1597c-129">With [hybrid cloud solutions](https://azure.microsoft.com/solutions/hybrid-cloud-app/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1597c-130">[Anterior](manage-production-docker-environments.md)
>[Siguiente](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="1597c-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>

---
title: Supervisión de servicios de aplicaciones en contenedor
description: Obtenga información sobre algunos aspectos clave de supervisión de las arquitecturas de contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4553a35c8db6cfc46187525ef2ffc65cb3ba07c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672053"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="e1a96-103">Supervisión de servicios de aplicaciones en contenedor</span><span class="sxs-lookup"><span data-stu-id="e1a96-103">Monitor containerized application services</span></span>

<span data-ttu-id="e1a96-104">Es fundamental para las aplicaciones que se divide en varios contenedores y microservicios tiene una forma de supervisar y analizar el comportamiento de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1a96-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="e1a96-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="e1a96-105">Azure Monitor</span></span>

<span data-ttu-id="e1a96-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) es un servicio de análisis extensible que supervisa la aplicación activa.</span><span class="sxs-lookup"><span data-stu-id="e1a96-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="e1a96-107">Le ayuda a detectar y diagnosticar problemas de rendimiento y comprender lo que los usuarios hacen con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1a96-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="e1a96-108">Está diseñado para desarrolladores, con la intención de ayudarle a mejorar continuamente el rendimiento y facilidad de uso de los servicios o aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e1a96-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="e1a96-109">Azure Monitor funciona con/servicios web e independiente aplicaciones en una amplia variedad de plataformas como. NET, Java, Node.js y muchas otras plataformas, hospedadas en local o en la nube.</span><span class="sxs-lookup"><span data-stu-id="e1a96-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e1a96-110">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e1a96-110">Additional resources</span></span>

- <span data-ttu-id="e1a96-111">**Información general sobre Azure Monitor** \\</span><span class="sxs-lookup"><span data-stu-id="e1a96-111">**Overview of Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="e1a96-112">**¿Qué es Application Insights?**</span><span class="sxs-lookup"><span data-stu-id="e1a96-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="e1a96-113">**¿Qué es la supervisión de las métricas de Azure?**</span><span class="sxs-lookup"><span data-stu-id="e1a96-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="e1a96-114">**Solución de supervisión de contenedores en Azure Monitor** \\</span><span class="sxs-lookup"><span data-stu-id="e1a96-114">**Container Monitoring solution in Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="e1a96-115">Servicios de seguridad y copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="e1a96-115">Security and backup services</span></span>

<span data-ttu-id="e1a96-116">Hay muchas tareas de soporte técnico con una gran cantidad de detalles que se deben controlar para garantizar que sus aplicaciones e infraestructura están en estado de la ranura superior para admitir las necesidades empresariales y la situación se vuelve más complicada en el dominio Kerberos de microservicios, por lo que necesita una manera de tiene vistas detalladas y de alto nivel cuando deba tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="e1a96-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="e1a96-117">Azure tiene las herramientas para administrar y proporcionar una vista unificada de cuatro aspectos críticos de recursos de la nube y el local:</span><span class="sxs-lookup"><span data-stu-id="e1a96-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="e1a96-118">**Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e1a96-118">**Security**.</span></span> <span data-ttu-id="e1a96-119">Con [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span><span class="sxs-lookup"><span data-stu-id="e1a96-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="e1a96-120">Obtenga total visibilidad y control sobre la seguridad de sus máquinas virtuales, aplicaciones y cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1a96-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="e1a96-121">Centralizar la administración de las directivas de seguridad e integrar herramientas y procesos existentes.</span><span class="sxs-lookup"><span data-stu-id="e1a96-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="e1a96-122">Detectar amenazas reales con análisis avanzado.</span><span class="sxs-lookup"><span data-stu-id="e1a96-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="e1a96-123">**Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e1a96-123">**Backup**.</span></span> <span data-ttu-id="e1a96-124">Con [copia de seguridad de Azure](https://azure.microsoft.com/services/backup/).</span><span class="sxs-lookup"><span data-stu-id="e1a96-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="e1a96-125">Evitar interrupciones empresariales costosas, cumplir los objetivos de cumplimiento normativo y proteja sus datos frente a ransomware y errores humanos.</span><span class="sxs-lookup"><span data-stu-id="e1a96-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="e1a96-126">Mantener los datos de copia de seguridad cifrados en tránsito y en reposo.</span><span class="sxs-lookup"><span data-stu-id="e1a96-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="e1a96-127">Asegúrese de acceso basado en la autenticación multifactor para evitar el uso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="e1a96-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="e1a96-128">**Los recursos locales**.</span><span class="sxs-lookup"><span data-stu-id="e1a96-128">**On-premises resources**.</span></span> <span data-ttu-id="e1a96-129">Con [una nube híbrida verdaderamente coherente](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span><span class="sxs-lookup"><span data-stu-id="e1a96-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e1a96-130">[Anterior](manage-production-docker-environments.md)
>[Siguiente](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="e1a96-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>

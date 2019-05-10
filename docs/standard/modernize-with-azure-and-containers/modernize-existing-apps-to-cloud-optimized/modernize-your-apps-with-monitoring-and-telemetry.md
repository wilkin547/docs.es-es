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
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="b7a11-103">Modernización de aplicaciones con supervisión y telemetría</span><span class="sxs-lookup"><span data-stu-id="b7a11-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="b7a11-104">Al ejecutar una aplicación en producción, es fundamental que dispone de información detallada sobre el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7a11-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="b7a11-105">¿Se ejecuta en un nivel alto?</span><span class="sxs-lookup"><span data-stu-id="b7a11-105">Is it performing at a high level?</span></span> <span data-ttu-id="b7a11-106">¿Los usuarios reciben errores o es la aplicación estable y confiable?</span><span class="sxs-lookup"><span data-stu-id="b7a11-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="b7a11-107">Se necesitan la supervisión de alto rendimiento, alertas y muy eficaces, paneles para ayudar a garantizar que la aplicación está disponible y funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="b7a11-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="b7a11-108">También deberá ser capaz de ver rápidamente si hay un problema, determine cuántos clientes se ven afectados y realizan un análisis de causa raíz para buscar y corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="b7a11-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="b7a11-109">Supervisar la aplicación con Application Insights</span><span class="sxs-lookup"><span data-stu-id="b7a11-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="b7a11-110">Application Insights es un servicio de Application Performance Management (APM) extensible para desarrolladores web que trabajan en varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="b7a11-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="b7a11-111">Usarlo para supervisar la aplicación web activa.</span><span class="sxs-lookup"><span data-stu-id="b7a11-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="b7a11-112">Application Insights detecta automáticamente las anomalías de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b7a11-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="b7a11-113">Incluye herramientas de análisis eficaces que le ayudarán a diagnosticar problemas y que le ayudarán a comprender lo que los usuarios hacen con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7a11-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="b7a11-114">Application Insights está diseñado para ayudarle a mejorar continuamente el rendimiento y facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="b7a11-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="b7a11-115">Funciona para las aplicaciones en una amplia variedad de plataformas, incluidas. NET, Node.js y J2EE, ya sean hospedados localmente o en la nube.</span><span class="sxs-lookup"><span data-stu-id="b7a11-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="b7a11-116">Application Insights se integra con los procesos de DevOps y tiene puntos de conexión a una variedad de herramientas de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b7a11-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="b7a11-117">Figura 4-10 se muestra un ejemplo de cómo Application Insights supervisa la aplicación y cómo presenta esa información a un panel.</span><span class="sxs-lookup"><span data-stu-id="b7a11-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Panel de supervisión de Application Insights](./media/image10.png)

> <span data-ttu-id="b7a11-119">**Figura 4-10.**</span><span class="sxs-lookup"><span data-stu-id="b7a11-119">**Figure 4-10.**</span></span> <span data-ttu-id="b7a11-120">Panel de supervisión de Application Insights</span><span class="sxs-lookup"><span data-stu-id="b7a11-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="b7a11-121">Supervisar la infraestructura de Docker con Log Analytics y su solución de supervisión de contenedores</span><span class="sxs-lookup"><span data-stu-id="b7a11-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="b7a11-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) forma parte de la [general de solución de supervisión de Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span><span class="sxs-lookup"><span data-stu-id="b7a11-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="b7a11-123">También es un servicio en [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="b7a11-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="b7a11-124">Log Analytics supervisa en la nube y entornos locales (OMS para un entorno local) para ayudar a mantener la disponibilidad y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b7a11-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="b7a11-125">Recopila los datos generados por los recursos en sus entornos de nube y locales y desde otras herramientas de supervisión para proporcionar análisis entre varios orígenes.</span><span class="sxs-lookup"><span data-stu-id="b7a11-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="b7a11-126">En relación con los registros de infraestructura de Azure Log Analytics, como un servicio de Azure ingiere datos de registro y métricas de otros servicios de Azure (a través de [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), máquinas virtuales de Azure, contenedores de Docker y en el entorno local u otras infraestructuras de nube.</span><span class="sxs-lookup"><span data-stu-id="b7a11-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="b7a11-127">Log Analytics ofrece búsqueda de registros flexible y análisis de fuera del cuadro en estos datos.</span><span class="sxs-lookup"><span data-stu-id="b7a11-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="b7a11-128">Proporciona herramientas enriquecidas que puede usar para analizar datos en orígenes, permite realizar consultas complejas en todos los registros y puede alertar de forma proactiva según las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="b7a11-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="b7a11-129">Incluso puede recopilar datos personalizados en el repositorio central de Log Analytics, donde puede consultarlos y visualizarlos.</span><span class="sxs-lookup"><span data-stu-id="b7a11-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="b7a11-130">También puede aprovechar las ventajas de las soluciones integradas de Log Analytics para obtener información sobre la seguridad de forma inmediata y la funcionalidad de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="b7a11-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="b7a11-131">Puede acceder a Log Analytics a través del portal de OMS o Azure portal, que se ejecutan en cualquier explorador, y proporcionar acceso a los valores de configuración y a varias herramientas para analizar y actuar sobre los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="b7a11-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="b7a11-132">El [solución de supervisión de contenedores](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) en Log Analytics le ayuda a ver y administrar los hosts de Docker y el contenedor de Windows en una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="b7a11-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="b7a11-133">La solución muestra qué contenedores están ejecutando, qué imagen de contenedor se están ejecutando y que se ejecutan los contenedores.</span><span class="sxs-lookup"><span data-stu-id="b7a11-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="b7a11-134">Puede ver información detallada de auditoría, incluidos los comandos que se usan con contenedores.</span><span class="sxs-lookup"><span data-stu-id="b7a11-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="b7a11-135">También puede solucionar los contenedores de ver y buscar registros centralizados, sin necesidad de ver los hosts de Docker o Windows de forma remota.</span><span class="sxs-lookup"><span data-stu-id="b7a11-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="b7a11-136">Puede encontrar los contenedores que podrían ser ruidoso y consumo excesivo de recursos en un host.</span><span class="sxs-lookup"><span data-stu-id="b7a11-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="b7a11-137">Además, puede ver centralizada CPU, memoria, almacenamiento y uso de la red y la información de rendimiento, para los contenedores.</span><span class="sxs-lookup"><span data-stu-id="b7a11-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="b7a11-138">En equipos que ejecutan Windows, puede centralizar y comparar registros de Windows Server, Hyper-V y contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="b7a11-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="b7a11-139">La solución admite los siguientes orquestadores de contenedor:</span><span class="sxs-lookup"><span data-stu-id="b7a11-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="b7a11-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="b7a11-140">Docker Swarm</span></span>

- <span data-ttu-id="b7a11-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="b7a11-141">DC/OS</span></span>

- <span data-ttu-id="b7a11-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="b7a11-142">Kubernetes</span></span>

- <span data-ttu-id="b7a11-143">Service Fabric</span><span class="sxs-lookup"><span data-stu-id="b7a11-143">Service Fabric</span></span>

- <span data-ttu-id="b7a11-144">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="b7a11-144">Red Hat OpenShift</span></span>

<span data-ttu-id="b7a11-145">Figura 4-11 muestra las relaciones entre varios hosts de contenedores y los agentes y OMS.</span><span class="sxs-lookup"><span data-stu-id="b7a11-145">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Solución de supervisión de contenedores de análisis de registro](./media/image11.png)

> <span data-ttu-id="b7a11-147">**Figura 4-11.**</span><span class="sxs-lookup"><span data-stu-id="b7a11-147">**Figure 4-11.**</span></span> <span data-ttu-id="b7a11-148">Solución de supervisión de contenedores de análisis de registro</span><span class="sxs-lookup"><span data-stu-id="b7a11-148">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="b7a11-149">Puede usar la solución de supervisión de contenedores de Log Analytics para:</span><span class="sxs-lookup"><span data-stu-id="b7a11-149">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="b7a11-150">Ver información sobre todos los hosts de contenedor en una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="b7a11-150">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="b7a11-151">Saber qué contenedores están ejecutando, qué imagen se están ejecutando y donde se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="b7a11-151">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="b7a11-152">Vea una pista de auditoría para las acciones en contenedores.</span><span class="sxs-lookup"><span data-stu-id="b7a11-152">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="b7a11-153">Solucionar errores viendo y buscar registros centralizados sin inicio de sesión remoto a los hosts de Docker.</span><span class="sxs-lookup"><span data-stu-id="b7a11-153">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="b7a11-154">Buscar contenedores que podrían ser "vecinos ruidosos" y se consumo excesivo de recursos en un host.</span><span class="sxs-lookup"><span data-stu-id="b7a11-154">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="b7a11-155">Ver centralizada CPU, memoria, almacenamiento y uso de la red y la información de rendimiento, para los contenedores.</span><span class="sxs-lookup"><span data-stu-id="b7a11-155">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b7a11-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b7a11-156">Additional resources</span></span>

- <span data-ttu-id="b7a11-157">**Información general de supervisión en Microsoft Azure**</span><span class="sxs-lookup"><span data-stu-id="b7a11-157">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="b7a11-158">**¿Qué es Application Insights?**</span><span class="sxs-lookup"><span data-stu-id="b7a11-158">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="b7a11-159">**¿Qué es Log Analytics?**</span><span class="sxs-lookup"><span data-stu-id="b7a11-159">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="b7a11-160">**Solución de supervisión de contenedores en Azure Monitor**</span><span class="sxs-lookup"><span data-stu-id="b7a11-160">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="b7a11-161">**Información general sobre Azure Monitor**</span><span class="sxs-lookup"><span data-stu-id="b7a11-161">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="b7a11-162">**¿Qué es Operations Management Suite (OMS)?**</span><span class="sxs-lookup"><span data-stu-id="b7a11-162">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

- <span data-ttu-id="b7a11-163">**Supervisión de contenedores de Windows Server en Service Fabric con OMS**</span><span class="sxs-lookup"><span data-stu-id="b7a11-163">**Monitoring Windows Server containers in Service Fabric with OMS**</span></span>

<https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver>

>[!div class="step-by-step"]
><span data-ttu-id="b7a11-164">[Anterior](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Siguiente](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="b7a11-164">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>

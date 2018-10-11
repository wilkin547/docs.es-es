---
title: Tabla de decisiones. Versiones de .NET Framework para su uso con Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Tabla de decisiones, versiones de .NET Framework para su uso con Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: 74b3749077fdb375f84ddacd98221aa4afcf2f67
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2018
ms.locfileid: "47401243"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="dc654-104">Tabla de decisiones: versiones de .NET Framework para su uso con Docker</span><span class="sxs-lookup"><span data-stu-id="dc654-104">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="dc654-105">En la siguiente tabla de decisiones se resume si se debe usar .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc654-105">The following decision table summarizes whether to use .NET Framework or .NET Core.</span></span> <span data-ttu-id="dc654-106">Recuerde que, para los contenedores de Linux, necesita hosts de Docker basados en Linux (máquinas virtuales o servidores) y, para los contenedores de Windows, necesita hosts de Docker basados en Windows Server (máquinas virtuales o servidores).</span><span class="sxs-lookup"><span data-stu-id="dc654-106">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc654-107">Los equipos de desarrollo ejecutarán un host de Docker, ya sea Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="dc654-107">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="dc654-108">Todos los microservicios relacionados que quiera ejecutar y probar juntos en una solución deberán ejecutarse en la misma plataforma de contenedor.</span><span class="sxs-lookup"><span data-stu-id="dc654-108">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="dc654-109"><strong>Arquitectura/tipo de aplicación</strong></span><span class="sxs-lookup"><span data-stu-id="dc654-109"><strong>Architecture / App Type</strong></span></span></th>
<th><span data-ttu-id="dc654-110"><strong>Contenedores de Linux</strong></span><span class="sxs-lookup"><span data-stu-id="dc654-110"><strong>Linux containers</strong></span></span></th>
<th><span data-ttu-id="dc654-111"><strong>Contenedores de Windows</strong></span><span class="sxs-lookup"><span data-stu-id="dc654-111"><strong>Windows Containers</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="dc654-112">Microservicios en contenedores</span><span class="sxs-lookup"><span data-stu-id="dc654-112">Microservices on containers</span></span></td>
<td><span data-ttu-id="dc654-113">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-113">.NET Core</span></span></td>
<td><span data-ttu-id="dc654-114">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-114">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc654-115">Aplicación monolítica</span><span class="sxs-lookup"><span data-stu-id="dc654-115">Monolithic app</span></span></td>
<td><span data-ttu-id="dc654-116">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-116">.NET Core</span></span></td>
<td><p><span data-ttu-id="dc654-117">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc654-117">.NET Framework</span></span></p>
<p><span data-ttu-id="dc654-118">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-118">.NET Core</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dc654-119">Rendimiento y escalabilidad líderes</span><span class="sxs-lookup"><span data-stu-id="dc654-119">Best-in-class performance and scalability</span></span></td>
<td><span data-ttu-id="dc654-120">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-120">.NET Core</span></span></td>
<td><span data-ttu-id="dc654-121">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-121">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc654-122">Migración de aplicación heredada de Windows Server ("brown-field") a contenedores</span><span class="sxs-lookup"><span data-stu-id="dc654-122">Windows Server legacy app ("brown-field") migration to containers</span></span></td>
<td>--</td>
<td><span data-ttu-id="dc654-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc654-123">.NET Framework</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dc654-124">Nuevo desarrollo basado en contenedor ("green-field")</span><span class="sxs-lookup"><span data-stu-id="dc654-124">New container-based development ("green-field")</span></span></td>
<td><span data-ttu-id="dc654-125">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-125">.NET Core</span></span></td>
<td><span data-ttu-id="dc654-126">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-126">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc654-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dc654-127">ASP.NET Core</span></span></td>
<td><span data-ttu-id="dc654-128">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-128">.NET Core</span></span></td>
<td><p><span data-ttu-id="dc654-129">.NET Core (recomendado)</span><span class="sxs-lookup"><span data-stu-id="dc654-129">.NET Core (recommended)</span></span></p>
<p><span data-ttu-id="dc654-130">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc654-130">.NET Framework</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dc654-131">ASP.NET 4 (MVC 5, API web 2 y formularios Web Forms)</span><span class="sxs-lookup"><span data-stu-id="dc654-131">ASP.NET 4 (MVC 5, Web API 2, and Web Forms)</span></span></td>
<td>--</td>
<td><span data-ttu-id="dc654-132">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc654-132">.NET Framework</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc654-133">Servicios SignalR</span><span class="sxs-lookup"><span data-stu-id="dc654-133">SignalR services</span></span></td>
<td><span data-ttu-id="dc654-134">.NET Core 2.1 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="dc654-134">.NET Core 2.1 or higher version</span></span></td>
<td><p><span data-ttu-id="dc654-135">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc654-135">.NET Framework</span></span></p>
<p><span data-ttu-id="dc654-136">.NET Core 2.1 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="dc654-136">.NET Core 2.1 or higher version</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dc654-137">WCF, WF y otros marcos heredados</span><span class="sxs-lookup"><span data-stu-id="dc654-137">WCF, WF, and other legacy frameworks</span></span></td>
<td><span data-ttu-id="dc654-138">WCF en .NET Core (solo la biblioteca cliente de WCF)</span><span class="sxs-lookup"><span data-stu-id="dc654-138">WCF in .NET Core (only the WCF client library)</span></span></td>
<td><p><span data-ttu-id="dc654-139">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc654-139">.NET Framework</span></span></p>
<p><span data-ttu-id="dc654-140">WCF en .NET Core (solo la biblioteca cliente de WCF)</span><span class="sxs-lookup"><span data-stu-id="dc654-140">WCF in .NET Core (only the WCF client library)</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dc654-141">Consumo de servicios de Azure</span><span class="sxs-lookup"><span data-stu-id="dc654-141">Consumption of Azure services</span></span></td>
<td><p><span data-ttu-id="dc654-142">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-142">.NET Core</span></span></p>
<p><span data-ttu-id="dc654-143">(finalmente todos los servicios de Azure proporcionarán el SDK de cliente para .NET Core)</span><span class="sxs-lookup"><span data-stu-id="dc654-143">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
<td><p><span data-ttu-id="dc654-144">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc654-144">.NET Framework</span></span></p>
<p><span data-ttu-id="dc654-145">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="dc654-145">.NET Core</span></span></p>
<p><span data-ttu-id="dc654-146">(finalmente todos los servicios de Azure proporcionarán el SDK de cliente para .NET Core)</span><span class="sxs-lookup"><span data-stu-id="dc654-146">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
<span data-ttu-id="dc654-147">[Anterior](net-framework-container-scenarios.md)
[Siguiente](net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="dc654-147">[Previous](net-framework-container-scenarios.md)
[Next](net-container-os-targets.md)</span></span>

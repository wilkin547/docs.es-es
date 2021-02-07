---
description: 'Más información acerca de: interfaz ICLRAppDomainResourceMonitor'
title: ICLRAppDomainResourceMonitor (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 85321eabedb6912efabe57553732f8c6a4063155
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753905"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="28698-103">ICLRAppDomainResourceMonitor (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28698-103">ICLRAppDomainResourceMonitor Interface</span></span>

<span data-ttu-id="28698-104">Proporciona métodos que inspeccionan el uso de la CPU y la memoria de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="28698-104">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28698-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="28698-105">Methods</span></span>  
  
|<span data-ttu-id="28698-106">Método</span><span class="sxs-lookup"><span data-stu-id="28698-106">Method</span></span>|<span data-ttu-id="28698-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="28698-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28698-108">Método GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="28698-108">GetCurrentAllocated Method</span></span>](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="28698-109">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recolectado como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="28698-109">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="28698-110">Método GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="28698-110">GetCurrentSurvived Method</span></span>](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="28698-111">Obtiene el número de bytes que sobrevivieron a la última recolección completa de elementos no utilizados bloqueada y a la que hace referencia el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="28698-111">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="28698-112">Método GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="28698-112">GetCurrentCpuTime Method</span></span>](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="28698-113">Obtiene el tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual, desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="28698-113">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28698-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="28698-114">Remarks</span></span>  

 <span data-ttu-id="28698-115">La `ICLRAppDomainResourceMonitor` interfaz proporciona una funcionalidad similar a las siguientes propiedades administradas:</span><span class="sxs-lookup"><span data-stu-id="28698-115">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="28698-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28698-116">Requirements</span></span>  

 <span data-ttu-id="28698-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28698-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28698-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="28698-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="28698-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28698-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28698-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28698-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28698-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="28698-121">See also</span></span>

- [<span data-ttu-id="28698-122">Elemento \<appDomainResourceMonitoring></span><span class="sxs-lookup"><span data-stu-id="28698-122">\<appDomainResourceMonitoring> Element</span></span>](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="28698-123">Supervisión de recursos del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="28698-123">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="28698-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="28698-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="28698-125">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="28698-125">Hosting</span></span>](index.md)

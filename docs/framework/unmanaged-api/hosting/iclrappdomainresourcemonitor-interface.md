---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 597381c8ab31e86a02f870a24f165676d200b66e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965014"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="4efa0-102">ICLRAppDomainResourceMonitor (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4efa0-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="4efa0-103">Proporciona métodos que inspeccionan el uso de la CPU y la memoria de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4efa0-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4efa0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4efa0-104">Methods</span></span>  
  
|<span data-ttu-id="4efa0-105">Método</span><span class="sxs-lookup"><span data-stu-id="4efa0-105">Method</span></span>|<span data-ttu-id="4efa0-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4efa0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4efa0-107">GetCurrentAllocated (método)</span><span class="sxs-lookup"><span data-stu-id="4efa0-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="4efa0-108">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recolectado como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="4efa0-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="4efa0-109">GetCurrentSurvived (método)</span><span class="sxs-lookup"><span data-stu-id="4efa0-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="4efa0-110">Obtiene el número de bytes que sobrevivieron a la última recolección completa de elementos no utilizados bloqueada y a la que hace referencia el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="4efa0-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="4efa0-111">GetCurrentCpuTime (método)</span><span class="sxs-lookup"><span data-stu-id="4efa0-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="4efa0-112">Obtiene el tiempo total de procesador usado por todos los subprocesos mientras se ejecutaba en el dominio de aplicación actual, desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4efa0-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4efa0-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4efa0-113">Remarks</span></span>  
 <span data-ttu-id="4efa0-114">La `ICLRAppDomainResourceMonitor` interfaz proporciona una funcionalidad similar a las siguientes propiedades administradas:</span><span class="sxs-lookup"><span data-stu-id="4efa0-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="4efa0-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4efa0-115">Requirements</span></span>  
 <span data-ttu-id="4efa0-116">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4efa0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4efa0-117">**Encabezado**: Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4efa0-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4efa0-118">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4efa0-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4efa0-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4efa0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efa0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4efa0-120">See also</span></span>

- [<span data-ttu-id="4efa0-121">\<appDomainResourceMonitoring >, elemento</span><span class="sxs-lookup"><span data-stu-id="4efa0-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="4efa0-122">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="4efa0-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="4efa0-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4efa0-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4efa0-124">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="4efa0-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

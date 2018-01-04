---
title: "ICLRAppDomainResourceMonitor::GetCurrentSurvived (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 612e27120196d2920b75c030929af1807d4a336f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="534b4-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived (Método)</span><span class="sxs-lookup"><span data-stu-id="534b4-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="534b4-103">Obtiene el número de bytes que sobrevivieron a la última recolección completa de bloqueo elementos no utilizados y que se hace referencia el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="534b4-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="534b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="534b4-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="534b4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="534b4-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="534b4-106">[in] El Id. del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="534b4-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="534b4-107">[out] Un puntero al número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que están contenidos en este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="534b4-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="534b4-108">Después de una recolección completa, este número es preciso y completo.</span><span class="sxs-lookup"><span data-stu-id="534b4-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="534b4-109">Después de una recolección efímera, este número puede estar incompleto.</span><span class="sxs-lookup"><span data-stu-id="534b4-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="534b4-110">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="534b4-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="534b4-111">[out] Un puntero al número total de bytes que sobrevivieron a la última recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="534b4-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="534b4-112">Después de una recolección completa, este número representa el número de bytes que se mantienen en montones administrados.</span><span class="sxs-lookup"><span data-stu-id="534b4-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="534b4-113">Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.</span><span class="sxs-lookup"><span data-stu-id="534b4-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="534b4-114">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="534b4-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="534b4-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="534b4-115">Return Value</span></span>  
 <span data-ttu-id="534b4-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="534b4-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="534b4-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="534b4-117">HRESULT</span></span>|<span data-ttu-id="534b4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="534b4-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="534b4-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="534b4-119">S_OK</span></span>|<span data-ttu-id="534b4-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="534b4-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="534b4-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="534b4-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="534b4-122">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="534b4-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="534b4-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="534b4-123">Remarks</span></span>  
 <span data-ttu-id="534b4-124">Las estadísticas se actualizan después de una recolección completa de bloqueo elementos no utilizados; es decir, se produce una colección que incluye todas las generaciones y que detiene la aplicación mientras la colección.</span><span class="sxs-lookup"><span data-stu-id="534b4-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="534b4-125">Por ejemplo, el <xref:System.GC.Collect?displayProperty=nameWithType> sobrecarga del método realiza una recolección completa de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="534b4-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="534b4-126">La recolección simultánea se produce en segundo plano y no bloquea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="534b4-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="534b4-127">El `GetCurrentSurvived` método es el equivalente administrado de los recursos administrados <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="534b4-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="534b4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="534b4-128">Requirements</span></span>  
 <span data-ttu-id="534b4-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="534b4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="534b4-130">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="534b4-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="534b4-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="534b4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="534b4-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="534b4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534b4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="534b4-133">See Also</span></span>  
 [<span data-ttu-id="534b4-134">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="534b4-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="534b4-135">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="534b4-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="534b4-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="534b4-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="534b4-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="534b4-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

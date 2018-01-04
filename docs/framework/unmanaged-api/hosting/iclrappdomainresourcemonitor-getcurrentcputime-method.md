---
title: "ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2781cfb1e23db02ab8192c78bd0a3e585ee28b2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="74fb0-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime (Método)</span><span class="sxs-lookup"><span data-stu-id="74fb0-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="74fb0-103">Obtiene el tiempo de procesador total que se ha utilizado por todos los subprocesos mientras se ejecutaban en el dominio de aplicación actual, desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74fb0-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74fb0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74fb0-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74fb0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74fb0-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="74fb0-106">[in] El Id. del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="74fb0-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="74fb0-107">[out] Un puntero al tiempo total de procesador que se ha utilizado por todos los subprocesos mientras se ejecutaban en el dominio de aplicación actual desde que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74fb0-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="74fb0-108">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="74fb0-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74fb0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74fb0-109">Return Value</span></span>  
  
|<span data-ttu-id="74fb0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74fb0-110">HRESULT</span></span>|<span data-ttu-id="74fb0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="74fb0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74fb0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="74fb0-112">S_OK</span></span>|<span data-ttu-id="74fb0-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="74fb0-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="74fb0-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="74fb0-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="74fb0-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="74fb0-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="74fb0-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74fb0-116">E_FAIL</span></span>|<span data-ttu-id="74fb0-117">No está habilitada la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="74fb0-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="74fb0-118">O bien</span><span class="sxs-lookup"><span data-stu-id="74fb0-118">-or-</span></span><br /><br /> <span data-ttu-id="74fb0-119">Todos los demás errores.</span><span class="sxs-lookup"><span data-stu-id="74fb0-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74fb0-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74fb0-120">Remarks</span></span>  
 <span data-ttu-id="74fb0-121">Este método es el equivalente administrado de los recursos administrados <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="74fb0-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74fb0-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74fb0-122">Requirements</span></span>  
 <span data-ttu-id="74fb0-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74fb0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74fb0-124">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="74fb0-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="74fb0-125">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74fb0-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74fb0-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74fb0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74fb0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="74fb0-127">See Also</span></span>  
 [<span data-ttu-id="74fb0-128">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74fb0-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="74fb0-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="74fb0-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="74fb0-130">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="74fb0-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="74fb0-131">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="74fb0-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

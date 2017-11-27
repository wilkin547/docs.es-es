---
title: "ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dee616e1fbd071662a42af856fa2cd51f7bdd5d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="70e96-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="70e96-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="70e96-103">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recopilado de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="70e96-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e96-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70e96-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70e96-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70e96-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="70e96-106">[in] El Id. del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="70e96-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="70e96-107">[out] Un puntero al tamaño total de todas las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="70e96-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70e96-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="70e96-108">Return Value</span></span>  
 <span data-ttu-id="70e96-109">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="70e96-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="70e96-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70e96-110">HRESULT</span></span>|<span data-ttu-id="70e96-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="70e96-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70e96-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="70e96-112">S_OK</span></span>|<span data-ttu-id="70e96-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="70e96-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="70e96-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="70e96-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="70e96-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="70e96-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70e96-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70e96-116">Remarks</span></span>  
 <span data-ttu-id="70e96-117">Este método es el equivalente administrado de los recursos administrados <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="70e96-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70e96-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70e96-118">Requirements</span></span>  
 <span data-ttu-id="70e96-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70e96-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70e96-120">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="70e96-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="70e96-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70e96-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70e96-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70e96-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e96-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="70e96-123">See Also</span></span>  
 [<span data-ttu-id="70e96-124">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70e96-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="70e96-125">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="70e96-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="70e96-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="70e96-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="70e96-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="70e96-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

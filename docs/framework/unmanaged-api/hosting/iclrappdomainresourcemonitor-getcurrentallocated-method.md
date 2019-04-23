---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fcd7a3aa1a6c034985099c24071429384563700
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129394"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="014bd-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="014bd-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="014bd-103">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria que el dominio de aplicación se han realizado desde que se creó, sin restar la memoria que se ha recopilado de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="014bd-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="014bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="014bd-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="014bd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="014bd-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="014bd-106">[in] El Id. del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="014bd-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="014bd-107">[out] Un puntero al tamaño total de todas las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="014bd-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="014bd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="014bd-108">Return Value</span></span>  
 <span data-ttu-id="014bd-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="014bd-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="014bd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="014bd-110">HRESULT</span></span>|<span data-ttu-id="014bd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="014bd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="014bd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="014bd-112">S_OK</span></span>|<span data-ttu-id="014bd-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="014bd-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="014bd-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="014bd-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="014bd-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="014bd-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="014bd-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="014bd-116">Remarks</span></span>  
 <span data-ttu-id="014bd-117">Este método es el equivalente administrado de los recursos administrados <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="014bd-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="014bd-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="014bd-118">Requirements</span></span>  
 <span data-ttu-id="014bd-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="014bd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="014bd-120">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="014bd-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="014bd-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="014bd-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="014bd-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="014bd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014bd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="014bd-123">See also</span></span>

- [<span data-ttu-id="014bd-124">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="014bd-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="014bd-125">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="014bd-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="014bd-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="014bd-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="014bd-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="014bd-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

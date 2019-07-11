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
ms.openlocfilehash: 19aced41860002081caaf6436bad08f5f9a09e9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766658"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="2b3d6-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="2b3d6-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="2b3d6-103">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria que el dominio de aplicación se han realizado desde que se creó, sin restar la memoria que se ha recopilado de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b3d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b3d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b3d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b3d6-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="2b3d6-106">[in] El Id. del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="2b3d6-107">[out] Un puntero al tamaño total de todas las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b3d6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2b3d6-108">Return Value</span></span>  
 <span data-ttu-id="2b3d6-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2b3d6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b3d6-110">HRESULT</span></span>|<span data-ttu-id="2b3d6-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2b3d6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b3d6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b3d6-112">S_OK</span></span>|<span data-ttu-id="2b3d6-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="2b3d6-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="2b3d6-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="2b3d6-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b3d6-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b3d6-116">Remarks</span></span>  
 <span data-ttu-id="2b3d6-117">Este método es el equivalente administrado de los recursos administrados <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b3d6-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b3d6-118">Requirements</span></span>  
 <span data-ttu-id="2b3d6-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b3d6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b3d6-120">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2b3d6-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2b3d6-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b3d6-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b3d6-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b3d6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3d6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b3d6-123">See also</span></span>

- [<span data-ttu-id="2b3d6-124">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b3d6-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="2b3d6-125">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="2b3d6-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="2b3d6-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="2b3d6-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2b3d6-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="2b3d6-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

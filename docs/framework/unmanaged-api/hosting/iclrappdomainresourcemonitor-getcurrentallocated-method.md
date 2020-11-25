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
ms.openlocfilehash: d3bd948dfe4a5cf97e3e3e430f551e7bc6404690
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700800"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="3f33c-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="3f33c-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>

<span data-ttu-id="3f33c-103">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recolectado como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="3f33c-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f33c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f33c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f33c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f33c-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="3f33c-106">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="3f33c-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="3f33c-107">enuncia Puntero al tamaño total de todas las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="3f33c-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f33c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f33c-108">Return Value</span></span>  

 <span data-ttu-id="3f33c-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="3f33c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3f33c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f33c-110">HRESULT</span></span>|<span data-ttu-id="3f33c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f33c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f33c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f33c-112">S_OK</span></span>|<span data-ttu-id="3f33c-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3f33c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="3f33c-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="3f33c-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="3f33c-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="3f33c-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f33c-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f33c-116">Remarks</span></span>  

 <span data-ttu-id="3f33c-117">Este método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3f33c-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f33c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f33c-118">Requirements</span></span>  

 <span data-ttu-id="3f33c-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f33c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f33c-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="3f33c-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3f33c-121">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f33c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f33c-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f33c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f33c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f33c-123">See also</span></span>

- [<span data-ttu-id="3f33c-124">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f33c-124">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="3f33c-125">Supervisión de recursos del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="3f33c-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="3f33c-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="3f33c-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="3f33c-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3f33c-127">Hosting</span></span>](index.md)

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
ms.openlocfilehash: 685d303b31b8f8c20cbbdb8aec6fc127650aa32a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616052"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="825cd-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="825cd-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="825cd-103">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recolectado como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="825cd-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="825cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="825cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="825cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="825cd-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="825cd-106">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="825cd-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="825cd-107">enuncia Puntero al tamaño total de todas las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="825cd-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="825cd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="825cd-108">Return Value</span></span>  
 <span data-ttu-id="825cd-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="825cd-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="825cd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="825cd-110">HRESULT</span></span>|<span data-ttu-id="825cd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="825cd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="825cd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="825cd-112">S_OK</span></span>|<span data-ttu-id="825cd-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="825cd-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="825cd-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="825cd-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="825cd-115">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="825cd-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="825cd-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="825cd-116">Remarks</span></span>  
 <span data-ttu-id="825cd-117">Este método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="825cd-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="825cd-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="825cd-118">Requirements</span></span>  
 <span data-ttu-id="825cd-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="825cd-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="825cd-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="825cd-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="825cd-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="825cd-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="825cd-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="825cd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825cd-123">Consulta también</span><span class="sxs-lookup"><span data-stu-id="825cd-123">See also</span></span>

- [<span data-ttu-id="825cd-124">ICLRAppDomainResourceMonitor (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="825cd-124">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="825cd-125">Supervisión de recursos del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="825cd-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="825cd-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="825cd-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="825cd-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="825cd-127">Hosting</span></span>](index.md)

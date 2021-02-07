---
description: 'Más información sobre: ICLRAppDomainResourceMonitor:: Getcurrentallocated ((método)'
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
ms.openlocfilehash: d7aaf31f775a9d6e2af95cf1a832c78587a85fe1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753957"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="b0a6c-103">ICLRAppDomainResourceMonitor::GetCurrentAllocated (Método)</span><span class="sxs-lookup"><span data-stu-id="b0a6c-103">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>

<span data-ttu-id="b0a6c-104">Obtiene el tamaño total, en bytes, de todas las asignaciones de memoria realizadas por el dominio de aplicación desde que se creó, sin restar la memoria que se ha recolectado como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="b0a6c-104">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a6c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0a6c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0a6c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0a6c-106">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="b0a6c-107">de IDENTIFICADOR del dominio de aplicación solicitado.</span><span class="sxs-lookup"><span data-stu-id="b0a6c-107">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="b0a6c-108">enuncia Puntero al tamaño total de todas las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="b0a6c-108">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0a6c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b0a6c-109">Return Value</span></span>  

 <span data-ttu-id="b0a6c-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="b0a6c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b0a6c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0a6c-111">HRESULT</span></span>|<span data-ttu-id="b0a6c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0a6c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0a6c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0a6c-113">S_OK</span></span>|<span data-ttu-id="b0a6c-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0a6c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b0a6c-115">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="b0a6c-115">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="b0a6c-116">El dominio de aplicación se ha descargado o no existe.</span><span class="sxs-lookup"><span data-stu-id="b0a6c-116">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0a6c-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b0a6c-117">Remarks</span></span>  

 <span data-ttu-id="b0a6c-118">Este método es el equivalente no administrado de la propiedad administrada <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b0a6c-118">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a6c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0a6c-119">Requirements</span></span>  

 <span data-ttu-id="b0a6c-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0a6c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a6c-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="b0a6c-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b0a6c-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0a6c-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0a6c-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a6c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a6c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0a6c-124">See also</span></span>

- [<span data-ttu-id="b0a6c-125">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0a6c-125">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="b0a6c-126">Supervisión de recursos del dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="b0a6c-126">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="b0a6c-127">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b0a6c-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b0a6c-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="b0a6c-128">Hosting</span></span>](index.md)

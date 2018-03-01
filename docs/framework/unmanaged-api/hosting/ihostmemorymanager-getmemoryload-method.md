---
title: "IHostMemoryManager::GetMemoryLoad (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 320881447eed00bf0dfeada0f5fbd224c32dfe96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="96885-102">IHostMemoryManager::GetMemoryLoad (Método)</span><span class="sxs-lookup"><span data-stu-id="96885-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="96885-103">Obtiene la cantidad de memoria física que está actualmente en uso y, por tanto, no está disponible, como notificado por el host.</span><span class="sxs-lookup"><span data-stu-id="96885-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96885-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96885-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96885-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96885-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="96885-106">[out] Un puntero al porcentaje aproximado de memoria física total que está actualmente en uso.</span><span class="sxs-lookup"><span data-stu-id="96885-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="96885-107">[out] Un puntero al número de bytes disponible para common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="96885-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96885-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="96885-108">Return Value</span></span>  
  
|<span data-ttu-id="96885-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96885-109">HRESULT</span></span>|<span data-ttu-id="96885-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="96885-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96885-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="96885-111">S_OK</span></span>|<span data-ttu-id="96885-112">`GetMemoryLoad`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="96885-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="96885-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="96885-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="96885-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="96885-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="96885-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96885-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="96885-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="96885-116">The call timed out.</span></span>|  
|<span data-ttu-id="96885-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="96885-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="96885-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="96885-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="96885-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="96885-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="96885-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="96885-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="96885-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96885-121">E_FAIL</span></span>|<span data-ttu-id="96885-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="96885-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96885-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="96885-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="96885-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="96885-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96885-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96885-125">Remarks</span></span>  
 <span data-ttu-id="96885-126">`GetMemoryLoad`ajusta el Win32 `GlobalMemoryStatus` función.</span><span class="sxs-lookup"><span data-stu-id="96885-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="96885-127">El valor de `pMemoryLoad` es el equivalente de la `dwMemoryLoad` campo el `MEMORYSTATUS` estructura devuelta desde `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="96885-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="96885-128">El runtime usa el valor devuelto como heurístico para el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="96885-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="96885-129">Por ejemplo, si el host informa de que la mayoría de memoria en uso, el recolector de elementos no utilizados puede elegir recopilar de varias generaciones para aumentar la cantidad de memoria que potencialmente puede estar disponible.</span><span class="sxs-lookup"><span data-stu-id="96885-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96885-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96885-130">Requirements</span></span>  
 <span data-ttu-id="96885-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96885-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96885-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96885-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96885-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96885-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96885-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96885-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96885-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="96885-135">See Also</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
 [<span data-ttu-id="96885-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96885-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)

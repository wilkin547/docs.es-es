---
title: IHostMemoryManager::GetMemoryLoad (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176284"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="aca4e-102">IHostMemoryManager::GetMemoryLoad (Método)</span><span class="sxs-lookup"><span data-stu-id="aca4e-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="aca4e-103">Obtiene la cantidad de memoria física que está actualmente en uso y, por lo tanto, no está disponible, según lo informado por el host.</span><span class="sxs-lookup"><span data-stu-id="aca4e-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca4e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aca4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aca4e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aca4e-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="aca4e-106">[fuera] Puntero al porcentaje aproximado de memoria física total que está actualmente en uso.</span><span class="sxs-lookup"><span data-stu-id="aca4e-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="aca4e-107">[fuera] Puntero al número de bytes disponibles para Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="aca4e-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aca4e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aca4e-108">Return Value</span></span>  
  
|<span data-ttu-id="aca4e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aca4e-109">HRESULT</span></span>|<span data-ttu-id="aca4e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca4e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aca4e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aca4e-111">S_OK</span></span>|<span data-ttu-id="aca4e-112">`GetMemoryLoad`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="aca4e-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="aca4e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aca4e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aca4e-114">El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="aca4e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aca4e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aca4e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aca4e-116">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="aca4e-116">The call timed out.</span></span>|  
|<span data-ttu-id="aca4e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aca4e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aca4e-118">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="aca4e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aca4e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aca4e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aca4e-120">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="aca4e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aca4e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aca4e-121">E_FAIL</span></span>|<span data-ttu-id="aca4e-122">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="aca4e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aca4e-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="aca4e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aca4e-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aca4e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aca4e-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aca4e-125">Remarks</span></span>  
 <span data-ttu-id="aca4e-126">`GetMemoryLoad`envuelve la función Win32. `GlobalMemoryStatus`</span><span class="sxs-lookup"><span data-stu-id="aca4e-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="aca4e-127">El valor `pMemoryLoad` de es `dwMemoryLoad` el equivalente `MEMORYSTATUS` del `GlobalMemoryStatus`campo en la estructura devuelta desde .</span><span class="sxs-lookup"><span data-stu-id="aca4e-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="aca4e-128">El tiempo de ejecución utiliza el valor devuelto como heurístico para el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="aca4e-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="aca4e-129">Por ejemplo, si el host informa de que la mayoría de la memoria está en uso, el recolector de elementos no utilizados puede optar por recopilar de varias generaciones para aumentar la cantidad de memoria que puede estar disponible.</span><span class="sxs-lookup"><span data-stu-id="aca4e-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aca4e-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aca4e-130">Requirements</span></span>  
 <span data-ttu-id="aca4e-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aca4e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aca4e-132">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="aca4e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aca4e-133">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aca4e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aca4e-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aca4e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca4e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aca4e-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="aca4e-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aca4e-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)

---
description: 'Más información acerca de: IHostMemoryManager:: GetMemoryLoad ((método)'
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
ms.openlocfilehash: 82288e6a705b014c2768c75e15376f7e6a0af428
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707852"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="28c2e-103">IHostMemoryManager::GetMemoryLoad (Método)</span><span class="sxs-lookup"><span data-stu-id="28c2e-103">IHostMemoryManager::GetMemoryLoad Method</span></span>

<span data-ttu-id="28c2e-104">Obtiene la cantidad de memoria física que está actualmente en uso y, por lo tanto, no está disponible, tal y como lo ha indicado el host.</span><span class="sxs-lookup"><span data-stu-id="28c2e-104">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c2e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28c2e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28c2e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28c2e-106">Parameters</span></span>  

 `pMemoryLoad`  
 <span data-ttu-id="28c2e-107">enuncia Un puntero al porcentaje aproximado de la memoria física total que se está usando actualmente.</span><span class="sxs-lookup"><span data-stu-id="28c2e-107">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="28c2e-108">enuncia Puntero al número de bytes disponibles para el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="28c2e-108">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28c2e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28c2e-109">Return Value</span></span>  
  
|<span data-ttu-id="28c2e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28c2e-110">HRESULT</span></span>|<span data-ttu-id="28c2e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="28c2e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28c2e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="28c2e-112">S_OK</span></span>|<span data-ttu-id="28c2e-113">`GetMemoryLoad` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="28c2e-113">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="28c2e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28c2e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28c2e-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="28c2e-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="28c2e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28c2e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28c2e-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="28c2e-117">The call timed out.</span></span>|  
|<span data-ttu-id="28c2e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28c2e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28c2e-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="28c2e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28c2e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28c2e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28c2e-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="28c2e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28c2e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28c2e-122">E_FAIL</span></span>|<span data-ttu-id="28c2e-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="28c2e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28c2e-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="28c2e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28c2e-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="28c2e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28c2e-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="28c2e-126">Remarks</span></span>  

 <span data-ttu-id="28c2e-127">`GetMemoryLoad` ajusta la función de Win32 `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="28c2e-127">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="28c2e-128">El valor de `pMemoryLoad` es el equivalente del `dwMemoryLoad` campo en la `MEMORYSTATUS` estructura devuelta desde `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="28c2e-128">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="28c2e-129">El motor en tiempo de ejecución utiliza el valor devuelto como una heurística para el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="28c2e-129">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="28c2e-130">Por ejemplo, si el host informa de que la mayoría de la memoria está en uso, el recolector de elementos no utilizados puede optar por recopilar de varias generaciones para aumentar la cantidad de memoria que podría estar disponible.</span><span class="sxs-lookup"><span data-stu-id="28c2e-130">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28c2e-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28c2e-131">Requirements</span></span>  

 <span data-ttu-id="28c2e-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28c2e-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28c2e-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="28c2e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28c2e-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28c2e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28c2e-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28c2e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c2e-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="28c2e-136">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="28c2e-137">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28c2e-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)

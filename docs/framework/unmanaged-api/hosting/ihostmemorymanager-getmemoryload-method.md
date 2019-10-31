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
ms.openlocfilehash: 2210dcd9e8a8af92b7905ec680c53c1119e6a3cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136707"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="bad37-102">IHostMemoryManager::GetMemoryLoad (Método)</span><span class="sxs-lookup"><span data-stu-id="bad37-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="bad37-103">Obtiene la cantidad de memoria física que está actualmente en uso y, por lo tanto, no está disponible, tal y como lo ha indicado el host.</span><span class="sxs-lookup"><span data-stu-id="bad37-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad37-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bad37-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad37-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bad37-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="bad37-106">enuncia Un puntero al porcentaje aproximado de la memoria física total que se está usando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bad37-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="bad37-107">enuncia Puntero al número de bytes disponibles para el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bad37-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bad37-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bad37-108">Return Value</span></span>  
  
|<span data-ttu-id="bad37-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bad37-109">HRESULT</span></span>|<span data-ttu-id="bad37-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bad37-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bad37-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bad37-111">S_OK</span></span>|<span data-ttu-id="bad37-112">`GetMemoryLoad` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bad37-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="bad37-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bad37-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bad37-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bad37-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bad37-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bad37-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bad37-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bad37-116">The call timed out.</span></span>|  
|<span data-ttu-id="bad37-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bad37-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bad37-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bad37-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bad37-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bad37-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bad37-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="bad37-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bad37-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bad37-121">E_FAIL</span></span>|<span data-ttu-id="bad37-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="bad37-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bad37-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bad37-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bad37-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bad37-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bad37-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bad37-125">Remarks</span></span>  
 <span data-ttu-id="bad37-126">`GetMemoryLoad` incluye la función de `GlobalMemoryStatus` de Win32.</span><span class="sxs-lookup"><span data-stu-id="bad37-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="bad37-127">El valor de `pMemoryLoad` es el equivalente del campo `dwMemoryLoad` de la estructura `MEMORYSTATUS` devuelta de `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="bad37-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="bad37-128">El motor en tiempo de ejecución utiliza el valor devuelto como una heurística para el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bad37-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="bad37-129">Por ejemplo, si el host informa de que la mayoría de la memoria está en uso, el recolector de elementos no utilizados puede optar por recopilar de varias generaciones para aumentar la cantidad de memoria que podría estar disponible.</span><span class="sxs-lookup"><span data-stu-id="bad37-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad37-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bad37-130">Requirements</span></span>  
 <span data-ttu-id="bad37-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad37-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad37-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bad37-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bad37-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bad37-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bad37-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad37-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad37-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="bad37-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="bad37-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bad37-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)

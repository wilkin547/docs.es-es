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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53001d6dfef2813df86dc4bb4f9647900143aae7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469071"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="89eba-102">IHostMemoryManager::GetMemoryLoad (Método)</span><span class="sxs-lookup"><span data-stu-id="89eba-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="89eba-103">Obtiene la cantidad de memoria física que está actualmente en uso y por lo tanto, no está disponible, como la información proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="89eba-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89eba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89eba-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89eba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89eba-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="89eba-106">[out] Un puntero al porcentaje aproximado de memoria física total que está actualmente en uso.</span><span class="sxs-lookup"><span data-stu-id="89eba-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="89eba-107">[out] Un puntero al número de bytes disponible para common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="89eba-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89eba-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="89eba-108">Return Value</span></span>  
  
|<span data-ttu-id="89eba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89eba-109">HRESULT</span></span>|<span data-ttu-id="89eba-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="89eba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89eba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="89eba-111">S_OK</span></span>|<span data-ttu-id="89eba-112">`GetMemoryLoad` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="89eba-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="89eba-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89eba-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89eba-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="89eba-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89eba-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89eba-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89eba-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="89eba-116">The call timed out.</span></span>|  
|<span data-ttu-id="89eba-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89eba-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89eba-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="89eba-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89eba-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89eba-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89eba-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="89eba-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89eba-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89eba-121">E_FAIL</span></span>|<span data-ttu-id="89eba-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="89eba-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89eba-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="89eba-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89eba-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89eba-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89eba-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89eba-125">Remarks</span></span>  
 <span data-ttu-id="89eba-126">`GetMemoryLoad` ajusta el Win32 `GlobalMemoryStatus` función.</span><span class="sxs-lookup"><span data-stu-id="89eba-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="89eba-127">El valor de `pMemoryLoad` equivale a la `dwMemoryLoad` campo el `MEMORYSTATUS` estructura devuelta desde `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="89eba-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="89eba-128">El runtime usa el valor devuelto como un método heurístico para el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="89eba-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="89eba-129">Por ejemplo, si el host informa de que la mayoría de la memoria está en uso, puede optar por el recolector de elementos no utilizados recopilar de varias generaciones para aumentar la cantidad de memoria que potencialmente puede estar disponible.</span><span class="sxs-lookup"><span data-stu-id="89eba-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89eba-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89eba-130">Requirements</span></span>  
 <span data-ttu-id="89eba-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89eba-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89eba-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89eba-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89eba-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89eba-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89eba-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89eba-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89eba-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="89eba-135">See also</span></span>
- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="89eba-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89eba-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)

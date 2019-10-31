---
title: IHostSyncManager::CreateSemaphore (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 02066d3923714e66bf287f1435b7854280c97cb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195825"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="14734-102">IHostSyncManager::CreateSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="14734-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="14734-103">Crea un objeto [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) para el Common Language Runtime (CLR) que se va a usar como semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="14734-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14734-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14734-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14734-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14734-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="14734-106">de Recuento inicial de `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="14734-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="14734-107">de Recuento máximo de `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="14734-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="14734-108">enuncia Puntero a la dirección de una instancia de `IHostSemaphore`, o null si no se pudo crear el semáforo.</span><span class="sxs-lookup"><span data-stu-id="14734-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14734-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14734-109">Return Value</span></span>  
  
|<span data-ttu-id="14734-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14734-110">HRESULT</span></span>|<span data-ttu-id="14734-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="14734-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14734-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="14734-112">S_OK</span></span>|<span data-ttu-id="14734-113">`CreateSemaphore` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="14734-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="14734-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14734-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14734-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="14734-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14734-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14734-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14734-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="14734-117">The call timed out.</span></span>|  
|<span data-ttu-id="14734-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14734-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14734-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="14734-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14734-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14734-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14734-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="14734-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14734-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14734-122">E_FAIL</span></span>|<span data-ttu-id="14734-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="14734-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14734-124">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="14734-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14734-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="14734-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="14734-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="14734-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="14734-127">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="14734-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14734-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14734-128">Remarks</span></span>  
 <span data-ttu-id="14734-129">`CreateSemaphore` refleja la función de Win32 que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="14734-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="14734-130">Los parámetros `dwInitial` y `dwMax` usan la misma semántica para el recuento de semáforos que los parámetros `lInitialCount` y `lMaximumCount` de Win32, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="14734-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="14734-131">`dwInitial` debe estar entre cero y `dwMax`, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="14734-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="14734-132">`dwMax` debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="14734-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14734-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14734-133">Requirements</span></span>  
 <span data-ttu-id="14734-134">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14734-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14734-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="14734-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14734-136">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="14734-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14734-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14734-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14734-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="14734-138">See also</span></span>

- [<span data-ttu-id="14734-139">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14734-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="14734-140">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14734-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="14734-141">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14734-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

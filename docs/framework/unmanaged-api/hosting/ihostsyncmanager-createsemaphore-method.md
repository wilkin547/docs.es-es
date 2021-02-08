---
description: 'Más información acerca de: IHostSyncManager:: Createsemaphore ((método)'
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
ms.openlocfilehash: 5a03ef7532e2ac8357ec015b40cc54942f5420e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784748"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="60f4d-103">IHostSyncManager::CreateSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="60f4d-103">IHostSyncManager::CreateSemaphore Method</span></span>

<span data-ttu-id="60f4d-104">Crea un objeto [IHostSemaphore](ihostsemaphore-interface.md) para el Common Language Runtime (CLR) que se va a usar como semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="60f4d-104">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60f4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60f4d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60f4d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60f4d-106">Parameters</span></span>  

 `dwInitial`  
 <span data-ttu-id="60f4d-107">de Número inicial de `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="60f4d-107">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="60f4d-108">de Número máximo de `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="60f4d-108">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="60f4d-109">enuncia Puntero a la dirección de una `IHostSemaphore` instancia de o null si no se pudo crear el semáforo.</span><span class="sxs-lookup"><span data-stu-id="60f4d-109">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60f4d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="60f4d-110">Return Value</span></span>  
  
|<span data-ttu-id="60f4d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60f4d-111">HRESULT</span></span>|<span data-ttu-id="60f4d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="60f4d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60f4d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="60f4d-113">S_OK</span></span>|<span data-ttu-id="60f4d-114">`CreateSemaphore` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="60f4d-114">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="60f4d-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="60f4d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60f4d-116">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="60f4d-116">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60f4d-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60f4d-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60f4d-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="60f4d-118">The call timed out.</span></span>|  
|<span data-ttu-id="60f4d-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60f4d-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60f4d-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="60f4d-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60f4d-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60f4d-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60f4d-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="60f4d-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60f4d-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60f4d-123">E_FAIL</span></span>|<span data-ttu-id="60f4d-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="60f4d-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60f4d-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="60f4d-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60f4d-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="60f4d-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="60f4d-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="60f4d-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="60f4d-128">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="60f4d-128">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60f4d-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="60f4d-129">Remarks</span></span>  

 <span data-ttu-id="60f4d-130">`CreateSemaphore` refleja la función de Win32 que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="60f4d-130">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="60f4d-131">Los `dwInitial` `dwMax` parámetros y usan la misma semántica para el recuento de semáforos que los `lInitialCount` parámetros y de Win32 `lMaximumCount` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="60f4d-131">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="60f4d-132">`dwInitial` debe estar entre cero y `dwMax` , ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="60f4d-132">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="60f4d-133">`dwMax` debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="60f4d-133">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60f4d-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60f4d-134">Requirements</span></span>  

 <span data-ttu-id="60f4d-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60f4d-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60f4d-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="60f4d-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60f4d-137">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60f4d-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60f4d-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f4d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f4d-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="60f4d-139">See also</span></span>

- [<span data-ttu-id="60f4d-140">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60f4d-140">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="60f4d-141">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60f4d-141">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="60f4d-142">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60f4d-142">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)

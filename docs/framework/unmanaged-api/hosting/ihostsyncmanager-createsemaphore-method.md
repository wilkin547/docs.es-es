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
ms.openlocfilehash: 680280e959d523356b95a5a4d9390c80720c0330
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803137"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="70783-102">IHostSyncManager::CreateSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="70783-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="70783-103">Crea un objeto [IHostSemaphore](ihostsemaphore-interface.md) para el Common Language Runtime (CLR) que se va a usar como semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="70783-103">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70783-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70783-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70783-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70783-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="70783-106">de Número inicial de `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="70783-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="70783-107">de Número máximo de `ppSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="70783-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="70783-108">enuncia Puntero a la dirección de una `IHostSemaphore` instancia de o null si no se pudo crear el semáforo.</span><span class="sxs-lookup"><span data-stu-id="70783-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70783-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="70783-109">Return Value</span></span>  
  
|<span data-ttu-id="70783-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70783-110">HRESULT</span></span>|<span data-ttu-id="70783-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="70783-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70783-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="70783-112">S_OK</span></span>|<span data-ttu-id="70783-113">`CreateSemaphore`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="70783-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="70783-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="70783-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="70783-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="70783-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="70783-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="70783-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="70783-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="70783-117">The call timed out.</span></span>|  
|<span data-ttu-id="70783-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="70783-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="70783-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="70783-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="70783-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="70783-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="70783-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="70783-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="70783-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="70783-122">E_FAIL</span></span>|<span data-ttu-id="70783-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="70783-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="70783-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="70783-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="70783-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="70783-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="70783-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="70783-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="70783-127">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="70783-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70783-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70783-128">Remarks</span></span>  
 <span data-ttu-id="70783-129">`CreateSemaphore`refleja la función de Win32 que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="70783-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="70783-130">Los `dwInitial` `dwMax` parámetros y usan la misma semántica para el recuento de semáforos que los `lInitialCount` parámetros y de Win32 `lMaximumCount` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="70783-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="70783-131">`dwInitial`debe estar entre cero y `dwMax` , ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="70783-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="70783-132">`dwMax`debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="70783-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70783-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70783-133">Requirements</span></span>  
 <span data-ttu-id="70783-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70783-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70783-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="70783-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70783-136">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="70783-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70783-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70783-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70783-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70783-138">See also</span></span>

- [<span data-ttu-id="70783-139">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70783-139">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="70783-140">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70783-140">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="70783-141">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70783-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)

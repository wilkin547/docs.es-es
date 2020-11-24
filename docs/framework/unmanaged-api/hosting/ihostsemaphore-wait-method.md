---
title: IHostSemaphore::Wait (Método)
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
ms.openlocfilehash: 69b2338e6992c386a3cd34a632d69b73a67f14fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683009"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="26352-102">IHostSemaphore::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="26352-102">IHostSemaphore::Wait Method</span></span>

<span data-ttu-id="26352-103">Hace que la instancia actual de [IHostSemaphore](ihostsemaphore-interface.md) espere hasta que sea propiedad o transcurra el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="26352-103">Causes the current [IHostSemaphore](ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26352-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26352-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26352-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26352-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="26352-106">de Número de milisegundos que se va a esperar antes de devolver, si la `IHostSemaphore` instancia actual no es propiedad.</span><span class="sxs-lookup"><span data-stu-id="26352-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="26352-107">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que especifica qué acción debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="26352-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26352-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="26352-108">Return Value</span></span>  
  
|<span data-ttu-id="26352-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="26352-109">HRESULT</span></span>|<span data-ttu-id="26352-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="26352-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="26352-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="26352-111">S_OK</span></span>|<span data-ttu-id="26352-112">`Wait` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="26352-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="26352-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="26352-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="26352-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="26352-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="26352-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="26352-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="26352-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="26352-116">The call timed out.</span></span>|  
|<span data-ttu-id="26352-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="26352-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="26352-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="26352-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="26352-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="26352-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="26352-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="26352-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="26352-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="26352-121">E_FAIL</span></span>|<span data-ttu-id="26352-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="26352-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="26352-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="26352-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="26352-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="26352-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="26352-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="26352-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="26352-126">El host detectó un interbloqueo durante el intervalo de espera y eligió la `IHostSemaphore` instancia actual como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="26352-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26352-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26352-127">Requirements</span></span>  

 <span data-ttu-id="26352-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26352-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26352-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="26352-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26352-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26352-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26352-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26352-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26352-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26352-132">See also</span></span>

- [<span data-ttu-id="26352-133">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26352-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="26352-134">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26352-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="26352-135">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26352-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="26352-136">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26352-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="26352-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26352-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)

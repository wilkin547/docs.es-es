---
title: IHostManualEvent::Wait (Método)
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: 6d0276764a07d5bb202d66b653fdf5cb96320c08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804555"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="16018-102">IHostManualEvent::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="16018-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="16018-103">Hace que la instancia de [IHostManualEvent](ihostmanualevent-interface.md) actual espere hasta que sea propiedad o transcurra un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="16018-103">Causes the current [IHostManualEvent](ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16018-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16018-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16018-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16018-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="16018-106">de Número de milisegundos que se va a esperar antes de devolver, si la `IHostManualEvent` instancia actual no es propiedad.</span><span class="sxs-lookup"><span data-stu-id="16018-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="16018-107">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que indica la acción que debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="16018-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16018-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="16018-108">Return Value</span></span>  
  
|<span data-ttu-id="16018-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16018-109">HRESULT</span></span>|<span data-ttu-id="16018-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="16018-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16018-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="16018-111">S_OK</span></span>|<span data-ttu-id="16018-112">`Wait`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="16018-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="16018-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16018-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16018-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="16018-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16018-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16018-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16018-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="16018-116">The call timed out.</span></span>|  
|<span data-ttu-id="16018-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16018-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16018-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="16018-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16018-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16018-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16018-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="16018-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16018-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16018-121">E_FAIL</span></span>|<span data-ttu-id="16018-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="16018-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16018-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="16018-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16018-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="16018-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="16018-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="16018-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="16018-126">El host detectó un interbloqueo durante el intervalo de espera y eligió la `IHostManualEvent` instancia actual como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="16018-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16018-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16018-127">Requirements</span></span>  
 <span data-ttu-id="16018-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16018-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16018-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="16018-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16018-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="16018-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16018-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16018-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16018-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16018-132">See also</span></span>

- [<span data-ttu-id="16018-133">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16018-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="16018-134">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16018-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="16018-135">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16018-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="16018-136">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16018-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="16018-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16018-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)

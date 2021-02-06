---
description: 'Más información acerca de: ICLRTask:: Switche (método)'
title: ICLRTask::SwitchIn (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: 0bbcd2b9594a8ce465a1dcd7b5ae3f8a0799826d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636837"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="fd083-103">ICLRTask::SwitchIn (Método)</span><span class="sxs-lookup"><span data-stu-id="fd083-103">ICLRTask::SwitchIn Method</span></span>

<span data-ttu-id="fd083-104">Notifica a la Common Language Runtime (CLR) que la tarea que la instancia de [ICLRTask](iclrtask-interface.md) actual representa está ahora en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="fd083-104">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd083-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd083-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd083-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd083-106">Parameters</span></span>  

 `threadHandle`  
 <span data-ttu-id="fd083-107">de Identificador del subproceso físico en el que se está ejecutando la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="fd083-107">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd083-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd083-108">Return Value</span></span>  
  
|<span data-ttu-id="fd083-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd083-109">HRESULT</span></span>|<span data-ttu-id="fd083-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd083-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd083-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd083-111">S_OK</span></span>|<span data-ttu-id="fd083-112">`SwitchIn` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd083-112">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="fd083-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd083-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd083-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd083-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd083-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd083-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd083-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fd083-116">The call timed out.</span></span>|  
|<span data-ttu-id="fd083-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd083-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd083-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fd083-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd083-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd083-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd083-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="fd083-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd083-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd083-121">E_FAIL</span></span>|<span data-ttu-id="fd083-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="fd083-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd083-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fd083-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd083-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd083-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd083-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="fd083-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="fd083-126">`SwitchIn` se llamó a sin una llamada anterior al [método SwitchOut](iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-126">`SwitchIn` was called without an earlier call to [SwitchOut Method](iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd083-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fd083-127">Remarks</span></span>  

 <span data-ttu-id="fd083-128">El `threadHandle` parámetro representa un identificador para el subproceso del sistema operativo en el que se ha programado la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="fd083-128">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="fd083-129">Si se ha producido la suplantación en este subproceso, debe llamar a [IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md) antes de cambiar en la tarea.</span><span class="sxs-lookup"><span data-stu-id="fd083-129">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd083-130">Una llamada a `SwitchIn` sin una llamada anterior a `SwitchOut` produce un error con un valor HRESULT de HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="fd083-130">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd083-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd083-131">Requirements</span></span>  

 <span data-ttu-id="fd083-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd083-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd083-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd083-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd083-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd083-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd083-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd083-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd083-136">See also</span></span>

- [<span data-ttu-id="fd083-137">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd083-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="fd083-138">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd083-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="fd083-139">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd083-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="fd083-140">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd083-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

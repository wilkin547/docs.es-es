---
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
ms.openlocfilehash: e98ae17d55c74d32844da96137c258d076ebc2db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691075"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="8c01d-102">ICLRTask::SwitchIn (Método)</span><span class="sxs-lookup"><span data-stu-id="8c01d-102">ICLRTask::SwitchIn Method</span></span>

<span data-ttu-id="8c01d-103">Notifica a la Common Language Runtime (CLR) que la tarea que la instancia de [ICLRTask](iclrtask-interface.md) actual representa está ahora en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="8c01d-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c01d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c01d-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c01d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c01d-105">Parameters</span></span>  

 `threadHandle`  
 <span data-ttu-id="8c01d-106">de Identificador del subproceso físico en el que se está ejecutando la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="8c01d-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c01d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c01d-107">Return Value</span></span>  
  
|<span data-ttu-id="8c01d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c01d-108">HRESULT</span></span>|<span data-ttu-id="8c01d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c01d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c01d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c01d-110">S_OK</span></span>|<span data-ttu-id="8c01d-111">`SwitchIn` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c01d-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="8c01d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c01d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c01d-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c01d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c01d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c01d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c01d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c01d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8c01d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c01d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c01d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8c01d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c01d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c01d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c01d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="8c01d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c01d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c01d-120">E_FAIL</span></span>|<span data-ttu-id="8c01d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8c01d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c01d-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8c01d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c01d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8c01d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8c01d-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8c01d-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8c01d-125">`SwitchIn` se llamó a sin una llamada anterior al [método SwitchOut](iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="8c01d-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c01d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c01d-126">Remarks</span></span>  

 <span data-ttu-id="8c01d-127">El `threadHandle` parámetro representa un identificador para el subproceso del sistema operativo en el que se ha programado la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="8c01d-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="8c01d-128">Si se ha producido la suplantación en este subproceso, debe llamar a [IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md) antes de cambiar en la tarea.</span><span class="sxs-lookup"><span data-stu-id="8c01d-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c01d-129">Una llamada a `SwitchIn` sin una llamada anterior a `SwitchOut` produce un error con un valor HRESULT de HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="8c01d-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c01d-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c01d-130">Requirements</span></span>  

 <span data-ttu-id="8c01d-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c01d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c01d-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8c01d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c01d-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c01d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c01d-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c01d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c01d-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c01d-135">See also</span></span>

- [<span data-ttu-id="8c01d-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c01d-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8c01d-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c01d-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8c01d-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c01d-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8c01d-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c01d-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

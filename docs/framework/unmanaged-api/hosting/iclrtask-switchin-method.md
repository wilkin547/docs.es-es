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
ms.openlocfilehash: d8f57af459d1bb3f338cfbfcbb29f69f533ea927
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762934"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="454c2-102">ICLRTask::SwitchIn (Método)</span><span class="sxs-lookup"><span data-stu-id="454c2-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="454c2-103">Notifica a la Common Language Runtime (CLR) que la tarea que la instancia de [ICLRTask](iclrtask-interface.md) actual representa está ahora en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="454c2-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="454c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="454c2-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="454c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="454c2-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="454c2-106">de Identificador del subproceso físico en el que se está ejecutando la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="454c2-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="454c2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="454c2-107">Return Value</span></span>  
  
|<span data-ttu-id="454c2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="454c2-108">HRESULT</span></span>|<span data-ttu-id="454c2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="454c2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="454c2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="454c2-110">S_OK</span></span>|<span data-ttu-id="454c2-111">`SwitchIn`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="454c2-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="454c2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="454c2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="454c2-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="454c2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="454c2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="454c2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="454c2-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="454c2-115">The call timed out.</span></span>|  
|<span data-ttu-id="454c2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="454c2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="454c2-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="454c2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="454c2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="454c2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="454c2-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="454c2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="454c2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="454c2-120">E_FAIL</span></span>|<span data-ttu-id="454c2-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="454c2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="454c2-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="454c2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="454c2-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="454c2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="454c2-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="454c2-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="454c2-125">`SwitchIn`se llamó a sin una llamada anterior al [método SwitchOut](iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="454c2-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="454c2-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="454c2-126">Remarks</span></span>  
 <span data-ttu-id="454c2-127">El `threadHandle` parámetro representa un identificador para el subproceso del sistema operativo en el que se ha programado la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="454c2-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="454c2-128">Si se ha producido la suplantación en este subproceso, debe llamar a [IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md) antes de cambiar en la tarea.</span><span class="sxs-lookup"><span data-stu-id="454c2-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="454c2-129">Una llamada a `SwitchIn` sin una llamada anterior a `SwitchOut` produce un error con un valor HRESULT de HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="454c2-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="454c2-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="454c2-130">Requirements</span></span>  
 <span data-ttu-id="454c2-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="454c2-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="454c2-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="454c2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="454c2-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="454c2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="454c2-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="454c2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="454c2-135">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="454c2-135">See also</span></span>

- [<span data-ttu-id="454c2-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="454c2-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="454c2-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="454c2-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="454c2-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="454c2-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="454c2-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="454c2-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

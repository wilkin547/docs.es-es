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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f408dd5e4d383040d9e3c03cd5bba8ebd320610f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938364"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="0986d-102">ICLRTask::SwitchIn (Método)</span><span class="sxs-lookup"><span data-stu-id="0986d-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="0986d-103">Notifica a la Common Language Runtime (CLR) que la tarea que la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) actual representa está ahora en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="0986d-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0986d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0986d-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0986d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0986d-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="0986d-106">de Identificador del subproceso físico en el que se está ejecutando la tarea representada por la instancia actual `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="0986d-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0986d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0986d-107">Return Value</span></span>  
  
|<span data-ttu-id="0986d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0986d-108">HRESULT</span></span>|<span data-ttu-id="0986d-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0986d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0986d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0986d-110">S_OK</span></span>|<span data-ttu-id="0986d-111">`SwitchIn`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0986d-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="0986d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0986d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0986d-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0986d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0986d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0986d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0986d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0986d-115">The call timed out.</span></span>|  
|<span data-ttu-id="0986d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0986d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0986d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0986d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0986d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0986d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0986d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0986d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0986d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0986d-120">E_FAIL</span></span>|<span data-ttu-id="0986d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0986d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0986d-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0986d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0986d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0986d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0986d-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="0986d-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="0986d-125">`SwitchIn`se llamó a sin una llamada anterior al [método SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="0986d-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0986d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0986d-126">Remarks</span></span>  
 <span data-ttu-id="0986d-127">El `threadHandle` parámetro representa un identificador para el subproceso del sistema operativo en el que se ha programado `ICLRTask` la tarea representada por la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="0986d-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="0986d-128">Si se ha producido la suplantación en este subproceso, debe llamar a [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) antes de cambiar en la tarea.</span><span class="sxs-lookup"><span data-stu-id="0986d-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0986d-129">Una llamada a `SwitchIn` sin una llamada anterior a `SwitchOut` produce un error con un valor HRESULT de HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="0986d-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0986d-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0986d-130">Requirements</span></span>  
 <span data-ttu-id="0986d-131">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0986d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0986d-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0986d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0986d-133">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0986d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0986d-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0986d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0986d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0986d-135">See also</span></span>

- [<span data-ttu-id="0986d-136">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0986d-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0986d-137">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0986d-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0986d-138">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0986d-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0986d-139">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0986d-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

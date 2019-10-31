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
ms.openlocfilehash: fbfd44c8e20bc75638d6356fe405f02790da8ac7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124620"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="7bcb1-102">ICLRTask::SwitchIn (Método)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="7bcb1-103">Notifica a la Common Language Runtime (CLR) que la tarea que la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) actual representa está ahora en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bcb1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bcb1-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bcb1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bcb1-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="7bcb1-106">de Identificador del subproceso físico en el que se está ejecutando la tarea representada por la instancia de `ICLRTask` actual.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bcb1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7bcb1-107">Return Value</span></span>  
  
|<span data-ttu-id="7bcb1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7bcb1-108">HRESULT</span></span>|<span data-ttu-id="7bcb1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7bcb1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7bcb1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7bcb1-110">S_OK</span></span>|<span data-ttu-id="7bcb1-111">`SwitchIn` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="7bcb1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7bcb1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7bcb1-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7bcb1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7bcb1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7bcb1-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-115">The call timed out.</span></span>|  
|<span data-ttu-id="7bcb1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7bcb1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7bcb1-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7bcb1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7bcb1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7bcb1-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7bcb1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7bcb1-120">E_FAIL</span></span>|<span data-ttu-id="7bcb1-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7bcb1-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7bcb1-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7bcb1-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="7bcb1-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="7bcb1-125">se llamó a `SwitchIn` sin una llamada anterior al [método SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="7bcb1-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bcb1-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7bcb1-126">Remarks</span></span>  
 <span data-ttu-id="7bcb1-127">El parámetro `threadHandle` representa un identificador para el subproceso del sistema operativo en el que se ha programado la tarea representada por la instancia de `ICLRTask` actual.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="7bcb1-128">Si se ha producido la suplantación en este subproceso, debe llamar a [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) antes de cambiar en la tarea.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bcb1-129">Una llamada a `SwitchIn` sin una llamada anterior a `SwitchOut` producirá un error con un valor HRESULT de HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bcb1-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bcb1-130">Requirements</span></span>  
 <span data-ttu-id="7bcb1-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bcb1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bcb1-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7bcb1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bcb1-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7bcb1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bcb1-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bcb1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcb1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bcb1-135">See also</span></span>

- [<span data-ttu-id="7bcb1-136">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7bcb1-137">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7bcb1-138">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7bcb1-139">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

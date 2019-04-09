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
ms.openlocfilehash: 5f36a963417aba082667bb9fb609e0d1dcad7b09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187686"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="2b326-102">ICLRTask::SwitchIn (Método)</span><span class="sxs-lookup"><span data-stu-id="2b326-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="2b326-103">Notifica a common language runtime (CLR) que la tarea que actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia representa ahora está en un estado operable.</span><span class="sxs-lookup"><span data-stu-id="2b326-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b326-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b326-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b326-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b326-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="2b326-106">[in] Un identificador para el subproceso físico en el que la tarea representada por el actual `ICLRTask` instancia se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2b326-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b326-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2b326-107">Return Value</span></span>  
  
|<span data-ttu-id="2b326-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b326-108">HRESULT</span></span>|<span data-ttu-id="2b326-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b326-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b326-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b326-110">S_OK</span></span>|`SwitchIn` <span data-ttu-id="2b326-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b326-111">returned successfully.</span></span>|  
|<span data-ttu-id="2b326-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b326-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b326-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b326-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b326-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b326-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b326-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2b326-115">The call timed out.</span></span>|  
|<span data-ttu-id="2b326-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b326-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b326-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2b326-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b326-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b326-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b326-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="2b326-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b326-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b326-120">E_FAIL</span></span>|<span data-ttu-id="2b326-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="2b326-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b326-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2b326-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b326-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2b326-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2b326-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="2b326-124">HOST_E_INVALIDOPERATION</span></span>|`SwitchIn` <span data-ttu-id="2b326-125">se invocó sin una llamada anterior a [SwitchOut (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="2b326-125">was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b326-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b326-126">Remarks</span></span>  
 <span data-ttu-id="2b326-127">El `threadHandle` parámetro representa un identificador para el subproceso del sistema operativo en el que la tarea representada por el actual `ICLRTask` se ha programado la instancia.</span><span class="sxs-lookup"><span data-stu-id="2b326-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="2b326-128">Si se ha producido la suplantación en este subproceso, se debe llamar a [IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) antes de cambiar a la tarea.</span><span class="sxs-lookup"><span data-stu-id="2b326-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b326-129">Una llamada a `SwitchIn` sin una llamada anterior a `SwitchOut` se produce un error con un valor HRESULT de HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="2b326-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b326-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b326-130">Requirements</span></span>  
 <span data-ttu-id="2b326-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b326-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b326-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2b326-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b326-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2b326-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2b326-134">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2b326-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2b326-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b326-135">See also</span></span>

- [<span data-ttu-id="2b326-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b326-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2b326-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b326-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2b326-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b326-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2b326-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b326-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

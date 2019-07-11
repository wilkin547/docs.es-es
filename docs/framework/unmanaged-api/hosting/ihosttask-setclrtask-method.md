---
title: IHostTask::SetCLRTask (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 884fedd6e8c2d79e895591e38b59cd3abb27275e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764394"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="4d9c4-102">IHostTask::SetCLRTask (Método)</span><span class="sxs-lookup"><span data-stu-id="4d9c4-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="4d9c4-103">Asocia un `ICLRTask` instancia con el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d9c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d9c4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d9c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d9c4-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="4d9c4-106">[in] Un puntero de interfaz a la `ICLRTask` instancia va a asociar con el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d9c4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d9c4-107">Return Value</span></span>  
  
|<span data-ttu-id="4d9c4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d9c4-108">HRESULT</span></span>|<span data-ttu-id="4d9c4-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4d9c4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d9c4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d9c4-110">S_OK</span></span>|<span data-ttu-id="4d9c4-111">`SetCLRTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="4d9c4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d9c4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d9c4-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d9c4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d9c4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d9c4-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-115">The call timed out.</span></span>|  
|<span data-ttu-id="4d9c4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d9c4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d9c4-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d9c4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d9c4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d9c4-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d9c4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d9c4-120">E_FAIL</span></span>|<span data-ttu-id="4d9c4-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d9c4-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d9c4-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4d9c4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d9c4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d9c4-124">Remarks</span></span>  
 <span data-ttu-id="4d9c4-125">CLR llama a `SetCLRTask` para asociar un `ICLRTask` instancia con el actual `IHostTask` instancia, que se creó mediante una llamada a [IHostTaskManager:: CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c4-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d9c4-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d9c4-126">Requirements</span></span>  
 <span data-ttu-id="4d9c4-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d9c4-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4d9c4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d9c4-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d9c4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d9c4-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d9c4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9c4-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d9c4-131">See also</span></span>

- [<span data-ttu-id="4d9c4-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d9c4-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4d9c4-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d9c4-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4d9c4-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d9c4-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4d9c4-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d9c4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

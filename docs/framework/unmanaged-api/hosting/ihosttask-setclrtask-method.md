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
ms.openlocfilehash: bbb563a304e3ff7cdba3dfe7e394da9cf138ff10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121370"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="a5622-102">IHostTask::SetCLRTask (Método)</span><span class="sxs-lookup"><span data-stu-id="a5622-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="a5622-103">Asocia una instancia de `ICLRTask` con la instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="a5622-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5622-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5622-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5622-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5622-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="a5622-106">de Puntero de interfaz a la instancia de `ICLRTask` que se va a asociar a la instancia de `IHostTask` actual.</span><span class="sxs-lookup"><span data-stu-id="a5622-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5622-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5622-107">Return Value</span></span>  
  
|<span data-ttu-id="a5622-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5622-108">HRESULT</span></span>|<span data-ttu-id="a5622-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5622-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5622-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5622-110">S_OK</span></span>|<span data-ttu-id="a5622-111">`SetCLRTask` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5622-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="a5622-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a5622-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a5622-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5622-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a5622-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a5622-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a5622-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a5622-115">The call timed out.</span></span>|  
|<span data-ttu-id="a5622-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a5622-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a5622-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a5622-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a5622-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a5622-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a5622-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a5622-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a5622-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a5622-120">E_FAIL</span></span>|<span data-ttu-id="a5622-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a5622-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a5622-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a5622-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a5622-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a5622-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5622-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5622-124">Remarks</span></span>  
 <span data-ttu-id="a5622-125">CLR llama `SetCLRTask` para asociar una instancia de `ICLRTask` a la instancia de `IHostTask` actual, que se creó mediante una llamada a [IHostTaskManager:: CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="a5622-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5622-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5622-126">Requirements</span></span>  
 <span data-ttu-id="a5622-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5622-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5622-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a5622-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5622-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5622-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5622-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5622-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5622-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5622-131">See also</span></span>

- [<span data-ttu-id="a5622-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5622-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a5622-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5622-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a5622-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5622-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a5622-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5622-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

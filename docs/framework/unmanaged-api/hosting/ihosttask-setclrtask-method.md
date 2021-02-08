---
description: 'Más información acerca de: IHostTask:: SetCLRTask ((método)'
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
ms.openlocfilehash: 381b7827f043b6ef1d4a6698f5eb103233c9af55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784683"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="5178d-103">IHostTask::SetCLRTask (Método)</span><span class="sxs-lookup"><span data-stu-id="5178d-103">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="5178d-104">Asocia una `ICLRTask` instancia de a la instancia de [IHostTask](ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="5178d-104">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5178d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5178d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5178d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5178d-106">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="5178d-107">de Puntero de interfaz a la `ICLRTask` instancia de que se va a asociar a la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="5178d-107">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5178d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5178d-108">Return Value</span></span>  
  
|<span data-ttu-id="5178d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5178d-109">HRESULT</span></span>|<span data-ttu-id="5178d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5178d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5178d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5178d-111">S_OK</span></span>|<span data-ttu-id="5178d-112">`SetCLRTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5178d-112">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="5178d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5178d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5178d-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5178d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5178d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5178d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5178d-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5178d-116">The call timed out.</span></span>|  
|<span data-ttu-id="5178d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5178d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5178d-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5178d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5178d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5178d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5178d-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5178d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5178d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5178d-121">E_FAIL</span></span>|<span data-ttu-id="5178d-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5178d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5178d-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5178d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5178d-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5178d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5178d-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5178d-125">Remarks</span></span>  

 <span data-ttu-id="5178d-126">CLR llama `SetCLRTask` a para asociar una `ICLRTask` instancia de a la `IHostTask` instancia actual, que se creó mediante una llamada a [IHostTaskManager:: CreateTask](ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="5178d-126">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5178d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5178d-127">Requirements</span></span>  

 <span data-ttu-id="5178d-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5178d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5178d-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5178d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5178d-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5178d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5178d-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5178d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5178d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5178d-132">See also</span></span>

- [<span data-ttu-id="5178d-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5178d-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5178d-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5178d-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5178d-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5178d-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5178d-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5178d-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

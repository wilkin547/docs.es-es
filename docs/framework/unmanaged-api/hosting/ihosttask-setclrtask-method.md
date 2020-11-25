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
ms.openlocfilehash: e6b9a4015a6139d6c8d7101fa7811c7ad9134e4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720469"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="c2d0d-102">IHostTask::SetCLRTask (Método)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-102">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="c2d0d-103">Asocia una `ICLRTask` instancia de a la instancia de [IHostTask](ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d0d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2d0d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2d0d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2d0d-105">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="c2d0d-106">de Puntero de interfaz a la `ICLRTask` instancia de que se va a asociar a la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2d0d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2d0d-107">Return Value</span></span>  
  
|<span data-ttu-id="c2d0d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2d0d-108">HRESULT</span></span>|<span data-ttu-id="c2d0d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2d0d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2d0d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2d0d-110">S_OK</span></span>|<span data-ttu-id="c2d0d-111">`SetCLRTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="c2d0d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2d0d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2d0d-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2d0d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2d0d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2d0d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c2d0d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2d0d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2d0d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2d0d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2d0d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2d0d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2d0d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2d0d-120">E_FAIL</span></span>|<span data-ttu-id="c2d0d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2d0d-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2d0d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2d0d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2d0d-124">Remarks</span></span>  

 <span data-ttu-id="c2d0d-125">CLR llama `SetCLRTask` a para asociar una `ICLRTask` instancia de a la `IHostTask` instancia actual, que se creó mediante una llamada a [IHostTaskManager:: CreateTask](ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="c2d0d-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2d0d-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2d0d-126">Requirements</span></span>  

 <span data-ttu-id="c2d0d-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2d0d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d0d-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c2d0d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2d0d-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2d0d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2d0d-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d0d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d0d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2d0d-131">See also</span></span>

- [<span data-ttu-id="c2d0d-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c2d0d-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c2d0d-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c2d0d-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

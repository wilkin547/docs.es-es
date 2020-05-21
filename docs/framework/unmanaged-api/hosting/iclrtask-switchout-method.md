---
title: ICLRTask::SwitchOut (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: 75517ae55ebae07242f19c19c5473780ce4b0809
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762921"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="c4e45-102">ICLRTask::SwitchOut (Método)</span><span class="sxs-lookup"><span data-stu-id="c4e45-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="c4e45-103">Notifica a la Common Language Runtime (CLR) que la tarea representada por la instancia de [ICLRTask](iclrtask-interface.md) actual ya no se encuentra en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="c4e45-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4e45-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c4e45-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c4e45-105">Return Value</span></span>  
  
|<span data-ttu-id="c4e45-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4e45-106">HRESULT</span></span>|<span data-ttu-id="c4e45-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4e45-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4e45-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4e45-108">S_OK</span></span>|<span data-ttu-id="c4e45-109">`SwitchOut`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c4e45-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="c4e45-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4e45-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4e45-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c4e45-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4e45-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4e45-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4e45-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c4e45-113">The call timed out.</span></span>|  
|<span data-ttu-id="c4e45-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4e45-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4e45-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c4e45-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4e45-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4e45-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4e45-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c4e45-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4e45-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4e45-118">E_FAIL</span></span>|<span data-ttu-id="c4e45-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c4e45-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4e45-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c4e45-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4e45-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c4e45-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4e45-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4e45-122">Remarks</span></span>  
 <span data-ttu-id="c4e45-123">Un host llama `SwitchOut` a para informar a CLR de que ha detenido temporalmente la ejecución de la tarea que `ICLRTask` representa la instancia actual y volverá a programar la tarea.</span><span class="sxs-lookup"><span data-stu-id="c4e45-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e45-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4e45-124">Requirements</span></span>  
 <span data-ttu-id="c4e45-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e45-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e45-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c4e45-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4e45-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c4e45-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4e45-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e45-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e45-129">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c4e45-129">See also</span></span>

- [<span data-ttu-id="c4e45-130">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4e45-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c4e45-131">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4e45-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c4e45-132">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4e45-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c4e45-133">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4e45-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

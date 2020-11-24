---
title: ICLRTask::RudeAbort (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 5b0e2265810b00fe0760d4e25c0f9904a96d9f2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691055"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="3703d-102">ICLRTask::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="3703d-102">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="3703d-103">Indica al Common Language Runtime (CLR) que anule la tarea representada por la instancia actual de la [interfaz ICLRTask](iclrtask-interface.md) inmediatamente y de forma incondicional.</span><span class="sxs-lookup"><span data-stu-id="3703d-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3703d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3703d-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="3703d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3703d-105">Return Value</span></span>  
  
|<span data-ttu-id="3703d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3703d-106">HRESULT</span></span>|<span data-ttu-id="3703d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3703d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3703d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3703d-108">S_OK</span></span>|<span data-ttu-id="3703d-109">`RudeAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3703d-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="3703d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3703d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3703d-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3703d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3703d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3703d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3703d-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3703d-113">The call timed out.</span></span>|  
|<span data-ttu-id="3703d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3703d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3703d-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3703d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3703d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3703d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3703d-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3703d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3703d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3703d-118">E_FAIL</span></span>|<span data-ttu-id="3703d-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3703d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3703d-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3703d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3703d-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3703d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3703d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3703d-122">Remarks</span></span>  

 <span data-ttu-id="3703d-123">Un host llama `RudeAbort` a para anular una tarea inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="3703d-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="3703d-124">No se garantiza que se ejecuten los finalizadores y las rutinas de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="3703d-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3703d-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3703d-125">Requirements</span></span>  

 <span data-ttu-id="3703d-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3703d-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3703d-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3703d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3703d-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3703d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3703d-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3703d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3703d-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3703d-130">See also</span></span>

- [<span data-ttu-id="3703d-131">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3703d-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="3703d-132">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3703d-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="3703d-133">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3703d-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="3703d-134">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3703d-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

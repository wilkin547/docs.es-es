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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e2145f321d2850468eaa73cc35a9dbd19af0480
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649493"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="e065a-102">ICLRTask::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="e065a-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="e065a-103">Indica a common language runtime (CLR) para cancelar la tarea representada por el actual [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia inmediatamente y de forma incondicional.</span><span class="sxs-lookup"><span data-stu-id="e065a-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e065a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e065a-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="e065a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e065a-105">Return Value</span></span>  
  
|<span data-ttu-id="e065a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e065a-106">HRESULT</span></span>|<span data-ttu-id="e065a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e065a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e065a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e065a-108">S_OK</span></span>|<span data-ttu-id="e065a-109">`RudeAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e065a-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="e065a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e065a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e065a-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e065a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e065a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e065a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e065a-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e065a-113">The call timed out.</span></span>|  
|<span data-ttu-id="e065a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e065a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e065a-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e065a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e065a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e065a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e065a-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="e065a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e065a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e065a-118">E_FAIL</span></span>|<span data-ttu-id="e065a-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="e065a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e065a-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="e065a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e065a-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e065a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e065a-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e065a-122">Remarks</span></span>  
 <span data-ttu-id="e065a-123">Un host llama `RudeAbort` anule inmediatamente una tarea.</span><span class="sxs-lookup"><span data-stu-id="e065a-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="e065a-124">Los finalizadores y las rutinas de control de excepciones no se garantiza que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="e065a-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e065a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e065a-125">Requirements</span></span>  
 <span data-ttu-id="e065a-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e065a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e065a-127">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e065a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e065a-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e065a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e065a-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e065a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e065a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e065a-130">See also</span></span>
- [<span data-ttu-id="e065a-131">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e065a-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e065a-132">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e065a-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e065a-133">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e065a-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e065a-134">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e065a-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

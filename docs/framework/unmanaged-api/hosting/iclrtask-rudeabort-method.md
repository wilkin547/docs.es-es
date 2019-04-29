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
ms.openlocfilehash: 2db47f90e73922858013885e99e953ddcacbd450
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763521"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="589b9-102">ICLRTask::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="589b9-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="589b9-103">Indica a common language runtime (CLR) para cancelar la tarea representada por el actual [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia inmediatamente y de forma incondicional.</span><span class="sxs-lookup"><span data-stu-id="589b9-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="589b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="589b9-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="589b9-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="589b9-105">Return Value</span></span>  
  
|<span data-ttu-id="589b9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="589b9-106">HRESULT</span></span>|<span data-ttu-id="589b9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="589b9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="589b9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="589b9-108">S_OK</span></span>|<span data-ttu-id="589b9-109">`RudeAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="589b9-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="589b9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="589b9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="589b9-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="589b9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="589b9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="589b9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="589b9-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="589b9-113">The call timed out.</span></span>|  
|<span data-ttu-id="589b9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="589b9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="589b9-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="589b9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="589b9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="589b9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="589b9-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="589b9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="589b9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="589b9-118">E_FAIL</span></span>|<span data-ttu-id="589b9-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="589b9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="589b9-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="589b9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="589b9-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="589b9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="589b9-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="589b9-122">Remarks</span></span>  
 <span data-ttu-id="589b9-123">Un host llama `RudeAbort` anule inmediatamente una tarea.</span><span class="sxs-lookup"><span data-stu-id="589b9-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="589b9-124">Los finalizadores y las rutinas de control de excepciones no se garantiza que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="589b9-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="589b9-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="589b9-125">Requirements</span></span>  
 <span data-ttu-id="589b9-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="589b9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="589b9-127">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="589b9-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="589b9-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="589b9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="589b9-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="589b9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589b9-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="589b9-130">See also</span></span>

- [<span data-ttu-id="589b9-131">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="589b9-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="589b9-132">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="589b9-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="589b9-133">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="589b9-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="589b9-134">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="589b9-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

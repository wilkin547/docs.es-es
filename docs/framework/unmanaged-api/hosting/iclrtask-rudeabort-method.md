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
ms.openlocfilehash: 69e3ecfc82985d52bd5b14e9faf2566e395b622b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124656"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="377f7-102">ICLRTask::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="377f7-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="377f7-103">Indica al Common Language Runtime (CLR) que anule la tarea representada por la instancia actual de la [interfaz ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) inmediatamente y de forma incondicional.</span><span class="sxs-lookup"><span data-stu-id="377f7-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="377f7-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="377f7-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="377f7-105">Return Value</span></span>  
  
|<span data-ttu-id="377f7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="377f7-106">HRESULT</span></span>|<span data-ttu-id="377f7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="377f7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="377f7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="377f7-108">S_OK</span></span>|<span data-ttu-id="377f7-109">`RudeAbort` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="377f7-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="377f7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="377f7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="377f7-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="377f7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="377f7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="377f7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="377f7-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="377f7-113">The call timed out.</span></span>|  
|<span data-ttu-id="377f7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="377f7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="377f7-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="377f7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="377f7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="377f7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="377f7-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="377f7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="377f7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="377f7-118">E_FAIL</span></span>|<span data-ttu-id="377f7-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="377f7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="377f7-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="377f7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="377f7-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="377f7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="377f7-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="377f7-122">Remarks</span></span>  
 <span data-ttu-id="377f7-123">Un host llama a `RudeAbort` para anular una tarea inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="377f7-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="377f7-124">No se garantiza que se ejecuten los finalizadores y las rutinas de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="377f7-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377f7-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="377f7-125">Requirements</span></span>  
 <span data-ttu-id="377f7-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="377f7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377f7-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="377f7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="377f7-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="377f7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="377f7-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377f7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377f7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="377f7-130">See also</span></span>

- [<span data-ttu-id="377f7-131">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="377f7-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="377f7-132">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="377f7-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="377f7-133">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="377f7-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="377f7-134">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="377f7-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

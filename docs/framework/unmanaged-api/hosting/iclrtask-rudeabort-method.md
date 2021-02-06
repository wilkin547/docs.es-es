---
description: 'Más información acerca de: ICLRTask:: RudeAbort ((método)'
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
ms.openlocfilehash: f152f11ce41018b458ed2cb4df255e486ad54da0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636889"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="17e32-103">ICLRTask::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="17e32-103">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="17e32-104">Indica al Common Language Runtime (CLR) que anule la tarea representada por la instancia actual de la [interfaz ICLRTask](iclrtask-interface.md) inmediatamente y de forma incondicional.</span><span class="sxs-lookup"><span data-stu-id="17e32-104">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e32-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17e32-105">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="17e32-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="17e32-106">Return Value</span></span>  
  
|<span data-ttu-id="17e32-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17e32-107">HRESULT</span></span>|<span data-ttu-id="17e32-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="17e32-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17e32-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="17e32-109">S_OK</span></span>|<span data-ttu-id="17e32-110">`RudeAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="17e32-110">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="17e32-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17e32-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17e32-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="17e32-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="17e32-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="17e32-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="17e32-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="17e32-114">The call timed out.</span></span>|  
|<span data-ttu-id="17e32-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="17e32-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="17e32-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="17e32-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="17e32-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="17e32-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="17e32-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="17e32-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="17e32-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17e32-119">E_FAIL</span></span>|<span data-ttu-id="17e32-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="17e32-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17e32-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="17e32-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="17e32-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="17e32-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17e32-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17e32-123">Remarks</span></span>  

 <span data-ttu-id="17e32-124">Un host llama `RudeAbort` a para anular una tarea inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="17e32-124">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="17e32-125">No se garantiza que se ejecuten los finalizadores y las rutinas de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="17e32-125">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17e32-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17e32-126">Requirements</span></span>  

 <span data-ttu-id="17e32-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17e32-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17e32-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="17e32-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17e32-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17e32-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17e32-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17e32-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e32-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="17e32-131">See also</span></span>

- [<span data-ttu-id="17e32-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17e32-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="17e32-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17e32-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="17e32-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17e32-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="17e32-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17e32-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)

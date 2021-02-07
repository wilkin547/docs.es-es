---
description: 'Más información acerca de: IHostTaskManager:: ReverseLeaveRuntime (método)'
title: IHostTaskManager::ReverseLeaveRuntime (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: 2fed157f6ea05243270b957cacdb00ba5a47a88f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680873"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="5d397-103">IHostTaskManager::ReverseLeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="5d397-103">IHostTaskManager::ReverseLeaveRuntime Method</span></span>

<span data-ttu-id="5d397-104">Notifica al host que el control está saliendo del Common Language Runtime (CLR) y entra en una función no administrada a la que se llama a su vez desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="5d397-104">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d397-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d397-105">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5d397-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d397-106">Return Value</span></span>  
  
|<span data-ttu-id="5d397-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d397-107">HRESULT</span></span>|<span data-ttu-id="5d397-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d397-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d397-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d397-109">S_OK</span></span>|<span data-ttu-id="5d397-110">`ReverseLeaveRuntime` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d397-110">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="5d397-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d397-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d397-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d397-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d397-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d397-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d397-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5d397-114">The call timed out.</span></span>|  
|<span data-ttu-id="5d397-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d397-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d397-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5d397-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d397-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d397-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d397-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5d397-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d397-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d397-119">E_FAIL</span></span>|<span data-ttu-id="5d397-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5d397-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d397-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5d397-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d397-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d397-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5d397-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5d397-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5d397-124">No hay suficiente memoria disponible para completar la asignación de recursos solicitada.</span><span class="sxs-lookup"><span data-stu-id="5d397-124">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d397-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5d397-125">Remarks</span></span>  

 <span data-ttu-id="5d397-126">CLR llama `ReverseLeaveRuntime` a para informar al host de que la tarea que se está ejecutando actualmente devuelve el control a una función no administrada que, a su vez, se ha llamado desde código administrado a través de la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="5d397-126">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="5d397-127">Cada llamada a `ReverseLeaveRuntime` coincide con una llamada correspondiente a [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="5d397-127">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d397-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d397-128">Requirements</span></span>  

 <span data-ttu-id="5d397-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d397-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d397-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5d397-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d397-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d397-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d397-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d397-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d397-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d397-133">See also</span></span>

- [<span data-ttu-id="5d397-134">Método CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="5d397-134">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="5d397-135">Método EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="5d397-135">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="5d397-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d397-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5d397-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d397-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5d397-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d397-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5d397-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d397-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="5d397-140">Método LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="5d397-140">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="5d397-141">[Aproximación a la invocación de plataforma](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5d397-141">[A Closer Look at Platform Invoke](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>

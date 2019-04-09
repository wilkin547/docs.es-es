---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cd3012d966c777749eb800b8986974a4e8d401f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154172"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="b99b0-102">IHostTaskManager::ReverseLeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="b99b0-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="b99b0-103">Notifica al host que el control está dejando common language runtime (CLR) y escribir una función no administrada que a su vez, se ha llamado desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="b99b0-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b99b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b99b0-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b99b0-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b99b0-105">Return Value</span></span>  
  
|<span data-ttu-id="b99b0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b99b0-106">HRESULT</span></span>|<span data-ttu-id="b99b0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b99b0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b99b0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b99b0-108">S_OK</span></span>|`ReverseLeaveRuntime` <span data-ttu-id="b99b0-109">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b99b0-109">returned successfully.</span></span>|  
|<span data-ttu-id="b99b0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b99b0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b99b0-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b99b0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b99b0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b99b0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b99b0-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b99b0-113">The call timed out.</span></span>|  
|<span data-ttu-id="b99b0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b99b0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b99b0-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b99b0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b99b0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b99b0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b99b0-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b99b0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b99b0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b99b0-118">E_FAIL</span></span>|<span data-ttu-id="b99b0-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b99b0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b99b0-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b99b0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b99b0-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b99b0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b99b0-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b99b0-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b99b0-123">No hay suficiente memoria disponible para completar la asignación de recursos solicitado.</span><span class="sxs-lookup"><span data-stu-id="b99b0-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b99b0-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b99b0-124">Remarks</span></span>  
 <span data-ttu-id="b99b0-125">CLR llama a `ReverseLeaveRuntime` para informar al host que la tarea está ejecuta actualmente está devolviendo el control a una función no administrada que a su vez, se ha llamado desde código administrado a través de la plataforma invocar.</span><span class="sxs-lookup"><span data-stu-id="b99b0-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="b99b0-126">Cada llamada a `ReverseLeaveRuntime` coincide con una llamada correspondiente a [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="b99b0-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b99b0-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b99b0-127">Requirements</span></span>  
 <span data-ttu-id="b99b0-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b99b0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b99b0-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b99b0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b99b0-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b99b0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b99b0-131">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b99b0-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b99b0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b99b0-132">See also</span></span>

- [<span data-ttu-id="b99b0-133">Método CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="b99b0-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="b99b0-134">Método EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="b99b0-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="b99b0-135">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b99b0-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b99b0-136">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b99b0-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b99b0-137">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b99b0-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b99b0-138">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b99b0-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="b99b0-139">Método LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="b99b0-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- [<span data-ttu-id="b99b0-140">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="b99b0-140">A Closer Look at Platform Invoke</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))

---
title: IHostTaskManager::ReverseEnterRuntime (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6eefdaf5dee423b0a9ae054446224a3ea97e3c9b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213784"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="350f7-102">IHostTaskManager::ReverseEnterRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="350f7-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="350f7-103">Notifica al host que se está realizando una llamada en common language runtime (CLR) de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="350f7-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="350f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="350f7-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="350f7-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="350f7-105">Return Value</span></span>  
  
|<span data-ttu-id="350f7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="350f7-106">HRESULT</span></span>|<span data-ttu-id="350f7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="350f7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="350f7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="350f7-108">S_OK</span></span>|`ReverseEnterRuntime` <span data-ttu-id="350f7-109">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="350f7-109">returned successfully.</span></span>|  
|<span data-ttu-id="350f7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="350f7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="350f7-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="350f7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="350f7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="350f7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="350f7-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="350f7-113">The call timed out.</span></span>|  
|<span data-ttu-id="350f7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="350f7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="350f7-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="350f7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="350f7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="350f7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="350f7-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="350f7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="350f7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="350f7-118">E_FAIL</span></span>|<span data-ttu-id="350f7-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="350f7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="350f7-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="350f7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="350f7-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="350f7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="350f7-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="350f7-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="350f7-123">No hay suficiente memoria disponible para completar la asignación de recursos solicitado.</span><span class="sxs-lookup"><span data-stu-id="350f7-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="350f7-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="350f7-124">Remarks</span></span>  
 <span data-ttu-id="350f7-125">Si se realiza la llamada a CLR de una secuencia que se ha originado en código administrado, con cada llamada a `ReverseEnterRuntime` corresponde a una llamada a [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="350f7-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="350f7-126">Las llamadas pueden originarse en código no administrado sin estar anidadas.</span><span class="sxs-lookup"><span data-stu-id="350f7-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="350f7-127">En este caso, no hay ninguna llamada a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), o `ReverseLeaveRuntime`y el número de llamadas a `ReverseEnterRuntime` no es igual el número de llamadas a `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="350f7-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="350f7-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="350f7-128">Requirements</span></span>  
 <span data-ttu-id="350f7-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="350f7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="350f7-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="350f7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="350f7-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="350f7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="350f7-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="350f7-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="350f7-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="350f7-133">See also</span></span>

- [<span data-ttu-id="350f7-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="350f7-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="350f7-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="350f7-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="350f7-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="350f7-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="350f7-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="350f7-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

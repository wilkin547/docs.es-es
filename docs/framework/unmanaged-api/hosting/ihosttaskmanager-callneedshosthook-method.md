---
title: IHostTaskManager::CallNeedsHostHook (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adc270be51988cba78c6e522b16b480baef725c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139235"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="32e1f-102">IHostTaskManager::CallNeedsHostHook (Método)</span><span class="sxs-lookup"><span data-stu-id="32e1f-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="32e1f-103">Permite especificar si common language runtime (CLR) puede alinear la llamada especificada a una función no administrada al host.</span><span class="sxs-lookup"><span data-stu-id="32e1f-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e1f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32e1f-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e1f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32e1f-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="32e1f-106">[in] La dirección dentro del archivo asignado portable ejecutable (PE) de la función no administrada que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="32e1f-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="32e1f-107">[out] Un puntero a un valor booleano que indica si el host requiere que la llamada a enlazarse.</span><span class="sxs-lookup"><span data-stu-id="32e1f-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32e1f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="32e1f-108">Return Value</span></span>  
  
|<span data-ttu-id="32e1f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32e1f-109">HRESULT</span></span>|<span data-ttu-id="32e1f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="32e1f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32e1f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="32e1f-111">S_OK</span></span>|`CallNeedsHostHook` <span data-ttu-id="32e1f-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="32e1f-112">returned successfully.</span></span>|  
|<span data-ttu-id="32e1f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32e1f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32e1f-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="32e1f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32e1f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32e1f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32e1f-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="32e1f-116">The call timed out.</span></span>|  
|<span data-ttu-id="32e1f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32e1f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32e1f-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="32e1f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32e1f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32e1f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32e1f-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="32e1f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32e1f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32e1f-121">E_FAIL</span></span>|<span data-ttu-id="32e1f-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="32e1f-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="32e1f-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="32e1f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32e1f-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32e1f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32e1f-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32e1f-125">Remarks</span></span>  
 <span data-ttu-id="32e1f-126">Para ayudar a optimizar la ejecución de código, el CLR realiza un análisis de cada plataforma de llamada de invocación durante la compilación para determinar si se puede alinear la llamada.</span><span class="sxs-lookup"><span data-stu-id="32e1f-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> `CallNeedsHostHook` <span data-ttu-id="32e1f-127">permite al host reemplazar esa decisión exigiendo que enlazarse una llamada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="32e1f-127">enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="32e1f-128">Si el host requiere un enlace, el tiempo de ejecución hace no insertada en la llamada.</span><span class="sxs-lookup"><span data-stu-id="32e1f-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="32e1f-129">El host normalmente requeriría un enlace donde debe ajustar un estado de punto flotante o tras recibir la notificación de que una llamada está entrando en un estado donde el host no puede realizar un seguimiento de las solicitudes del tiempo de ejecución de memoria o los bloqueos.</span><span class="sxs-lookup"><span data-stu-id="32e1f-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="32e1f-130">Cuando el host requiere que se enlace la llamada, el tiempo de ejecución notifica al host de las transiciones a y desde el código administrado mediante llamadas a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), y [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="32e1f-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e1f-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32e1f-131">Requirements</span></span>  
 <span data-ttu-id="32e1f-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e1f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e1f-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32e1f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32e1f-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32e1f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="32e1f-135">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="32e1f-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32e1f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="32e1f-136">See also</span></span>

- [<span data-ttu-id="32e1f-137">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32e1f-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="32e1f-138">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32e1f-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="32e1f-139">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32e1f-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="32e1f-140">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32e1f-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

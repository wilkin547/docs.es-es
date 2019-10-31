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
ms.openlocfilehash: f5a595651baa48553997c2cba138f4f61bd530f0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133102"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="604c1-102">IHostTaskManager::CallNeedsHostHook (Método)</span><span class="sxs-lookup"><span data-stu-id="604c1-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="604c1-103">Permite al host especificar si el Common Language Runtime (CLR) puede alinear la llamada especificada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="604c1-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="604c1-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="604c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="604c1-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="604c1-106">de Dirección dentro del archivo portable ejecutable (PE) asignado de la función no administrada a la que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="604c1-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="604c1-107">enuncia Un puntero a un valor booleano que indica si el host requiere que se enlace la llamada.</span><span class="sxs-lookup"><span data-stu-id="604c1-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="604c1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="604c1-108">Return Value</span></span>  
  
|<span data-ttu-id="604c1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="604c1-109">HRESULT</span></span>|<span data-ttu-id="604c1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="604c1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="604c1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="604c1-111">S_OK</span></span>|<span data-ttu-id="604c1-112">`CallNeedsHostHook` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="604c1-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="604c1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="604c1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="604c1-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="604c1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="604c1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="604c1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="604c1-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="604c1-116">The call timed out.</span></span>|  
|<span data-ttu-id="604c1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="604c1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="604c1-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="604c1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="604c1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="604c1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="604c1-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="604c1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="604c1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="604c1-121">E_FAIL</span></span>|<span data-ttu-id="604c1-122">Se ha producido un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="604c1-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="604c1-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="604c1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="604c1-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="604c1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="604c1-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="604c1-125">Remarks</span></span>  
 <span data-ttu-id="604c1-126">Para ayudar a optimizar la ejecución del código, CLR realiza un análisis de cada llamada de invocación de plataforma durante la compilación para determinar si la llamada se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="604c1-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="604c1-127">`CallNeedsHostHook` permite que el host invalide esa decisión solicitando que se enlace una llamada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="604c1-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="604c1-128">Si el host requiere un enlace, el runtime no insertará la llamada.</span><span class="sxs-lookup"><span data-stu-id="604c1-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="604c1-129">Normalmente, el host requeriría un enlace donde debe ajustar un estado de punto flotante o al recibir la notificación de que una llamada está entrando en un estado en el que el host no puede realizar el seguimiento de las solicitudes de memoria en tiempo de ejecución o de los bloqueos tomados.</span><span class="sxs-lookup"><span data-stu-id="604c1-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="604c1-130">Cuando el host requiere que se enlace la llamada, el tiempo de ejecución notifica al host de las transiciones hacia y desde el código administrado mediante llamadas a [EnterRuntime (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)y [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="604c1-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="604c1-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="604c1-131">Requirements</span></span>  
 <span data-ttu-id="604c1-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="604c1-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="604c1-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="604c1-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="604c1-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="604c1-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="604c1-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="604c1-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604c1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="604c1-136">See also</span></span>

- [<span data-ttu-id="604c1-137">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="604c1-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="604c1-138">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="604c1-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="604c1-139">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="604c1-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="604c1-140">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="604c1-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

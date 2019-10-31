---
title: ICLRPolicyManager::SetTimeoutAndAction (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: 3a58664a7dc81059214246b53cf967b50cd61063
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140741"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="15eff-102">ICLRPolicyManager::SetTimeoutAndAction (Método)</span><span class="sxs-lookup"><span data-stu-id="15eff-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="15eff-103">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="15eff-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15eff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15eff-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15eff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15eff-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="15eff-106">de Uno de los valores de [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , que indica la operación para la que se va a establecer el tiempo de espera y la Directiva `action`.</span><span class="sxs-lookup"><span data-stu-id="15eff-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="15eff-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="15eff-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="15eff-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="15eff-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="15eff-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="15eff-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="15eff-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="15eff-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="15eff-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="15eff-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="15eff-112">de Nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="15eff-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="15eff-113">Un valor de Infinite hace que `operation` nunca agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="15eff-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="15eff-114">de Uno de los valores de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , que indica la acción de la Directiva que el CLR debe realizar cuando se produce `operation`.</span><span class="sxs-lookup"><span data-stu-id="15eff-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15eff-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15eff-115">Return Value</span></span>  
  
|<span data-ttu-id="15eff-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15eff-116">HRESULT</span></span>|<span data-ttu-id="15eff-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="15eff-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15eff-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="15eff-118">S_OK</span></span>|<span data-ttu-id="15eff-119">`SetTimeoutAndAction` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="15eff-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="15eff-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15eff-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15eff-121">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="15eff-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15eff-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15eff-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15eff-123">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="15eff-123">The call timed out.</span></span>|  
|<span data-ttu-id="15eff-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15eff-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15eff-125">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="15eff-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15eff-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15eff-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15eff-127">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="15eff-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15eff-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15eff-128">E_FAIL</span></span>|<span data-ttu-id="15eff-129">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="15eff-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15eff-130">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="15eff-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15eff-131">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="15eff-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15eff-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="15eff-132">E_INVALIDARG</span></span>|<span data-ttu-id="15eff-133">No se puede establecer un tiempo de espera para el `operation`especificado o se proporcionó un valor no válido para `action`.</span><span class="sxs-lookup"><span data-stu-id="15eff-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15eff-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15eff-134">Remarks</span></span>  
 <span data-ttu-id="15eff-135">`SetTimeoutAndAction` encapsula las capacidades de los métodos [ICLRPolicyManager:: setTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) y [ICLRPolicyManager:: SetActionOnTimeout (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) , y se puede llamar en lugar de llamadas secuenciales a estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="15eff-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="15eff-136">No todos los valores de acción de Directiva se pueden especificar como el comportamiento de tiempo de espera para las operaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="15eff-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="15eff-137">Vea las secciones comentarios de los temas de estos dos métodos para ver los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="15eff-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15eff-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15eff-138">Requirements</span></span>  
 <span data-ttu-id="15eff-139">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15eff-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15eff-140">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="15eff-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15eff-141">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="15eff-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15eff-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15eff-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15eff-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="15eff-143">See also</span></span>

- [<span data-ttu-id="15eff-144">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="15eff-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="15eff-145">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="15eff-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="15eff-146">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15eff-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="15eff-147">SetActionOnTimeout (método)</span><span class="sxs-lookup"><span data-stu-id="15eff-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="15eff-148">ICLRPolicyManager:: SetTimeoutAndAction (</span><span class="sxs-lookup"><span data-stu-id="15eff-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)

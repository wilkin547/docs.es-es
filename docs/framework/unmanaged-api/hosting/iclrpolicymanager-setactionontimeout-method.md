---
title: ICLRPolicyManager::SetActionOnTimeout (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0f7989765dcec4c405d168d5fa3d082bc30512f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779833"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="b6262-102">ICLRPolicyManager::SetActionOnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="b6262-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="b6262-103">Especifica la acción de directiva que common language runtime (CLR) debe realizar cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="b6262-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6262-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6262-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6262-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6262-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="b6262-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica la operación que se va a especificar la acción de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b6262-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="b6262-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b6262-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="b6262-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="b6262-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="b6262-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="b6262-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="b6262-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b6262-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="b6262-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b6262-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="b6262-112">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción de directiva que se realizarán cuando se agota el tiempo de espera de la operación.</span><span class="sxs-lookup"><span data-stu-id="b6262-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6262-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6262-113">Return Value</span></span>  
  
|<span data-ttu-id="b6262-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6262-114">HRESULT</span></span>|<span data-ttu-id="b6262-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b6262-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6262-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6262-116">S_OK</span></span>|<span data-ttu-id="b6262-117">`SetActionOnTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6262-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="b6262-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b6262-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b6262-119">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6262-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b6262-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b6262-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b6262-121">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b6262-121">The call timed out.</span></span>|  
|<span data-ttu-id="b6262-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b6262-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b6262-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b6262-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b6262-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b6262-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b6262-125">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b6262-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b6262-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6262-126">E_FAIL</span></span>|<span data-ttu-id="b6262-127">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b6262-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6262-128">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b6262-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b6262-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b6262-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b6262-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b6262-130">E_INVALIDARG</span></span>|<span data-ttu-id="b6262-131">No se puede establecer un tiempo de espera para el elemento especificado `operation`, o se ha proporcionado un valor no válido para `operation`.</span><span class="sxs-lookup"><span data-stu-id="b6262-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6262-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6262-132">Remarks</span></span>  
 <span data-ttu-id="b6262-133">El valor de tiempo de espera puede ser el tiempo de espera predeterminado establecido por el CLR, o un valor especificado por el host en una llamada a la [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b6262-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="b6262-134">No todos los valores de acción de la directiva pueden especificarse como el comportamiento de tiempo de espera para las operaciones de CLR.</span><span class="sxs-lookup"><span data-stu-id="b6262-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="b6262-135">`SetActionOnTimeout` Normalmente se usa solo para escalar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b6262-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="b6262-136">Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones anulaciones de subprocesos, pero no se especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="b6262-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="b6262-137">La siguiente tabla describe los válido `action` valores para válido `operation` valores.</span><span class="sxs-lookup"><span data-stu-id="b6262-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="b6262-138">Valor de `operation`</span><span class="sxs-lookup"><span data-stu-id="b6262-138">Value for `operation`</span></span>|<span data-ttu-id="b6262-139">Valores válidos para `action`</span><span class="sxs-lookup"><span data-stu-id="b6262-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="b6262-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b6262-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="b6262-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b6262-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="b6262-142">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="b6262-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="b6262-143">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b6262-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="b6262-144">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b6262-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="b6262-145">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-145">-   eExitProcess</span></span><br /><span data-ttu-id="b6262-146">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="b6262-147">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="b6262-148">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="b6262-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="b6262-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="b6262-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="b6262-150">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b6262-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="b6262-151">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b6262-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="b6262-152">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-152">-   eExitProcess</span></span><br /><span data-ttu-id="b6262-153">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="b6262-154">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="b6262-155">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="b6262-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="b6262-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="b6262-156">OPR_ProcessExit</span></span>|<span data-ttu-id="b6262-157">-   eExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-157">-   eExitProcess</span></span><br /><span data-ttu-id="b6262-158">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="b6262-159">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="b6262-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="b6262-160">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="b6262-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6262-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6262-161">Requirements</span></span>  
 <span data-ttu-id="b6262-162">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6262-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6262-163">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b6262-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6262-164">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6262-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6262-165">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6262-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6262-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6262-166">See also</span></span>

- [<span data-ttu-id="b6262-167">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b6262-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="b6262-168">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b6262-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="b6262-169">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6262-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b6262-170">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6262-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)

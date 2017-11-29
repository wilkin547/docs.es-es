---
title: "ICLRPolicyManager::SetActionOnFailure (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5dc8e27ed1a5701886c3583a7515e4212f490208
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="3a41f-102">ICLRPolicyManager::SetActionOnFailure (Método)</span><span class="sxs-lookup"><span data-stu-id="3a41f-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="3a41f-103">Especifica la acción de directiva que common language runtime (CLR) debe realizar cuando se produce el error especificado.</span><span class="sxs-lookup"><span data-stu-id="3a41f-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a41f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a41f-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a41f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a41f-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="3a41f-106">[in] Uno de los [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valores, que indica el tipo de error que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="3a41f-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="3a41f-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción que se realizará cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="3a41f-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="3a41f-108">Para obtener una lista de valores admitidos, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="3a41f-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a41f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3a41f-109">Return Value</span></span>  
  
|<span data-ttu-id="3a41f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a41f-110">HRESULT</span></span>|<span data-ttu-id="3a41f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a41f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a41f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a41f-112">S_OK</span></span>|<span data-ttu-id="3a41f-113">`SetActionOnFailure`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a41f-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="3a41f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a41f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a41f-115">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a41f-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a41f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a41f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a41f-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3a41f-117">The call timed out.</span></span>|  
|<span data-ttu-id="3a41f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a41f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a41f-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3a41f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a41f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a41f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a41f-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="3a41f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a41f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a41f-122">E_FAIL</span></span>|<span data-ttu-id="3a41f-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="3a41f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a41f-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="3a41f-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a41f-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3a41f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3a41f-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3a41f-126">E_INVALIDARG</span></span>|<span data-ttu-id="3a41f-127">No se puede establecer una acción de directiva para la operación especificada, o se especifica una acción de directiva no válida para la operación.</span><span class="sxs-lookup"><span data-stu-id="3a41f-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a41f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a41f-128">Remarks</span></span>  
 <span data-ttu-id="3a41f-129">De forma predeterminada, CLR produce una excepción cuando se produce un error al asignar un recurso, como la memoria.</span><span class="sxs-lookup"><span data-stu-id="3a41f-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="3a41f-130">`SetActionOnFailure`permite al host invalidar este comportamiento mediante la especificación de la acción de directiva que se va a realizar en caso de error.</span><span class="sxs-lookup"><span data-stu-id="3a41f-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="3a41f-131">En la tabla siguiente se muestra las combinaciones de [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) y [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores que son compatibles.</span><span class="sxs-lookup"><span data-stu-id="3a41f-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="3a41f-132">(Se omite el prefijo FAIL_ de [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valores.)</span><span class="sxs-lookup"><span data-stu-id="3a41f-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="3a41f-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="3a41f-133">NonCriticalResource</span></span>|<span data-ttu-id="3a41f-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="3a41f-134">CriticalResource</span></span>|<span data-ttu-id="3a41f-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="3a41f-135">FatalRuntime</span></span>|<span data-ttu-id="3a41f-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="3a41f-136">OrphanedLock</span></span>|<span data-ttu-id="3a41f-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="3a41f-137">StackOverflow</span></span>|<span data-ttu-id="3a41f-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="3a41f-138">AccessViolation</span></span>|<span data-ttu-id="3a41f-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="3a41f-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="3a41f-140">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-140">X</span></span>|<span data-ttu-id="3a41f-141">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-141">X</span></span>||||<span data-ttu-id="3a41f-142">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-142">N/A</span></span>||  
|<span data-ttu-id="3a41f-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="3a41f-143">eThrowException</span></span>|<span data-ttu-id="3a41f-144">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-144">X</span></span>|<span data-ttu-id="3a41f-145">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-145">X</span></span>||||<span data-ttu-id="3a41f-146">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="3a41f-147">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-147">X</span></span>|<span data-ttu-id="3a41f-148">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-148">X</span></span>||||<span data-ttu-id="3a41f-149">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-149">N/A</span></span>|<span data-ttu-id="3a41f-150">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="3a41f-151">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-151">X</span></span>|<span data-ttu-id="3a41f-152">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-152">X</span></span>||||<span data-ttu-id="3a41f-153">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-153">N/A</span></span>|<span data-ttu-id="3a41f-154">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="3a41f-155">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-155">X</span></span>|<span data-ttu-id="3a41f-156">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-156">X</span></span>||<span data-ttu-id="3a41f-157">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-157">X</span></span>||<span data-ttu-id="3a41f-158">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-158">N/A</span></span>|<span data-ttu-id="3a41f-159">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="3a41f-160">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-160">X</span></span>|<span data-ttu-id="3a41f-161">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-161">X</span></span>||<span data-ttu-id="3a41f-162">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-162">X</span></span>|<span data-ttu-id="3a41f-163">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-163">X</span></span>|<span data-ttu-id="3a41f-164">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-164">N/A</span></span>|<span data-ttu-id="3a41f-165">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="3a41f-166">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-166">X</span></span>|<span data-ttu-id="3a41f-167">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-167">X</span></span>||<span data-ttu-id="3a41f-168">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-168">X</span></span>|<span data-ttu-id="3a41f-169">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-169">X</span></span>|<span data-ttu-id="3a41f-170">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-170">N/A</span></span>|<span data-ttu-id="3a41f-171">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-171">X</span></span>|  
|<span data-ttu-id="3a41f-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3a41f-172">eFastExitProcess</span></span>|<span data-ttu-id="3a41f-173">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-173">X</span></span>|<span data-ttu-id="3a41f-174">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-174">X</span></span>||<span data-ttu-id="3a41f-175">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-175">X</span></span>|<span data-ttu-id="3a41f-176">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-176">X</span></span>|<span data-ttu-id="3a41f-177">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="3a41f-178">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-178">X</span></span>|<span data-ttu-id="3a41f-179">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-179">X</span></span>|<span data-ttu-id="3a41f-180">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-180">X</span></span>|<span data-ttu-id="3a41f-181">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-181">X</span></span>|<span data-ttu-id="3a41f-182">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-182">X</span></span>|<span data-ttu-id="3a41f-183">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="3a41f-184">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-184">X</span></span>|<span data-ttu-id="3a41f-185">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-185">X</span></span>|<span data-ttu-id="3a41f-186">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-186">X</span></span>|<span data-ttu-id="3a41f-187">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-187">X</span></span>|<span data-ttu-id="3a41f-188">X</span><span class="sxs-lookup"><span data-stu-id="3a41f-188">X</span></span>|<span data-ttu-id="3a41f-189">N/D</span><span class="sxs-lookup"><span data-stu-id="3a41f-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="3a41f-190">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a41f-190">Requirements</span></span>  
 <span data-ttu-id="3a41f-191">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a41f-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a41f-192">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3a41f-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a41f-193">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a41f-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a41f-194">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a41f-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a41f-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a41f-195">See Also</span></span>  
 [<span data-ttu-id="3a41f-196">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="3a41f-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="3a41f-197">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="3a41f-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="3a41f-198">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a41f-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="3a41f-199">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a41f-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)

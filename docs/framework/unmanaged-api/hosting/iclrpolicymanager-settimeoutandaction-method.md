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
ms.openlocfilehash: 02e836601be72d54f561e077cd3c466470bafb25
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504100"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="04798-102">ICLRPolicyManager::SetTimeoutAndAction (Método)</span><span class="sxs-lookup"><span data-stu-id="04798-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="04798-103">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="04798-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04798-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04798-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04798-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04798-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="04798-106">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la operación para la que se va a establecer el tiempo de espera y la directiva `action` .</span><span class="sxs-lookup"><span data-stu-id="04798-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="04798-107">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="04798-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="04798-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="04798-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="04798-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="04798-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="04798-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="04798-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="04798-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="04798-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="04798-112">de Nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="04798-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="04798-113">Un valor de infinito hace que `operation` nunca agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="04798-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="04798-114">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción de la Directiva que el CLR debe realizar cuando `operation` se produce.</span><span class="sxs-lookup"><span data-stu-id="04798-114">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04798-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04798-115">Return Value</span></span>  
  
|<span data-ttu-id="04798-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04798-116">HRESULT</span></span>|<span data-ttu-id="04798-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="04798-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04798-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="04798-118">S_OK</span></span>|<span data-ttu-id="04798-119">`SetTimeoutAndAction`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="04798-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="04798-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04798-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04798-121">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="04798-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04798-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04798-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04798-123">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04798-123">The call timed out.</span></span>|  
|<span data-ttu-id="04798-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04798-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04798-125">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="04798-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04798-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04798-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04798-127">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="04798-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04798-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04798-128">E_FAIL</span></span>|<span data-ttu-id="04798-129">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="04798-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04798-130">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="04798-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04798-131">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04798-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="04798-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="04798-132">E_INVALIDARG</span></span>|<span data-ttu-id="04798-133">No se puede establecer un tiempo de espera para el especificado `operation` o se proporcionó un valor no válido para `action` .</span><span class="sxs-lookup"><span data-stu-id="04798-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04798-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04798-134">Remarks</span></span>  
 <span data-ttu-id="04798-135">`SetTimeoutAndAction`encapsula las capacidades de los métodos [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) y [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) , y se puede llamar en lugar de llamadas secuenciales a estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="04798-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="04798-136">No todos los valores de acción de Directiva se pueden especificar como el comportamiento de tiempo de espera para las operaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="04798-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="04798-137">Vea las secciones comentarios de los temas de estos dos métodos para ver los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="04798-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04798-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04798-138">Requirements</span></span>  
 <span data-ttu-id="04798-139">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04798-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04798-140">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04798-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04798-141">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04798-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04798-142">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04798-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04798-143">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="04798-143">See also</span></span>

- [<span data-ttu-id="04798-144">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="04798-144">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="04798-145">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="04798-145">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="04798-146">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04798-146">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="04798-147">Método SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="04798-147">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="04798-148">ICLRPolicyManager:: SetTimeoutAndAction (</span><span class="sxs-lookup"><span data-stu-id="04798-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](iclrpolicymanager-settimeoutandaction-method.md)

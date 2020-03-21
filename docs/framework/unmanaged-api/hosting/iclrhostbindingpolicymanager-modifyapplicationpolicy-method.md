---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178102"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="c25d1-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="c25d1-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="c25d1-103">Modifica la directiva de enlace para el ensamblado especificado y crea una nueva versión de la directiva.</span><span class="sxs-lookup"><span data-stu-id="c25d1-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c25d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c25d1-104">Syntax</span></span>  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c25d1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c25d1-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="c25d1-106">[en] La identidad del ensamblado que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="c25d1-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="c25d1-107">[en] La nueva identidad del ensamblado modificado.</span><span class="sxs-lookup"><span data-stu-id="c25d1-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="c25d1-108">[en] Puntero a un búfer que contiene los datos de directiva de enlace para que el ensamblado los modifique.</span><span class="sxs-lookup"><span data-stu-id="c25d1-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="c25d1-109">[en] El tamaño de la directiva de enlace que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="c25d1-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="c25d1-110">[en] Una combinación OR lógica de [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valores, que indica el control de redirección.</span><span class="sxs-lookup"><span data-stu-id="c25d1-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="c25d1-111">[fuera] Puntero a un búfer que contiene los nuevos datos de directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="c25d1-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="c25d1-112">[adentro, fuera] Un puntero al tamaño del nuevo búfer de directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="c25d1-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c25d1-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c25d1-113">Return Value</span></span>  
  
|<span data-ttu-id="c25d1-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c25d1-114">HRESULT</span></span>|<span data-ttu-id="c25d1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c25d1-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c25d1-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c25d1-116">S_OK</span></span>|<span data-ttu-id="c25d1-117">La directiva se modificó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c25d1-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="c25d1-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c25d1-118">E_INVALIDARG</span></span>|<span data-ttu-id="c25d1-119">`pwzSourceAssemblyIdentity`o `pwzTargetAssemblyIdentity` era una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="c25d1-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="c25d1-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c25d1-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c25d1-121">`pbNewApplicationPolicy` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="c25d1-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="c25d1-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c25d1-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c25d1-123">Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c25d1-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c25d1-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c25d1-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c25d1-125">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="c25d1-125">The call timed out.</span></span>|  
|<span data-ttu-id="c25d1-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c25d1-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c25d1-127">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="c25d1-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c25d1-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c25d1-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c25d1-129">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="c25d1-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c25d1-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c25d1-130">E_FAIL</span></span>|<span data-ttu-id="c25d1-131">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="c25d1-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c25d1-132">Después de que un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c25d1-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c25d1-133">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c25d1-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c25d1-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c25d1-134">Remarks</span></span>  
 <span data-ttu-id="c25d1-135">El `ModifyApplicationPolicy` método se puede llamar dos veces.</span><span class="sxs-lookup"><span data-stu-id="c25d1-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="c25d1-136">La primera llamada debe proporcionar `pbNewApplicationPolicy` un valor nulo para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="c25d1-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="c25d1-137">Esta llamada se devolverá `pcbNewAppPolicySize`con el valor necesario para .</span><span class="sxs-lookup"><span data-stu-id="c25d1-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="c25d1-138">La segunda llamada debe `pcbNewAppPolicySize`proporcionar este valor para , `pbNewApplicationPolicy`y apuntar a un búfer de ese tamaño para .</span><span class="sxs-lookup"><span data-stu-id="c25d1-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c25d1-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c25d1-139">Requirements</span></span>  
 <span data-ttu-id="c25d1-140">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c25d1-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c25d1-141">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="c25d1-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c25d1-142">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c25d1-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c25d1-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c25d1-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c25d1-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c25d1-144">See also</span></span>

- [<span data-ttu-id="c25d1-145">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c25d1-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07a4998f86958e21fffc8ba8657ec9f2a170f43e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984664"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="d578a-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="d578a-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="d578a-103">Modifica la directiva de enlace para el ensamblado especificado y crea una nueva versión de la directiva.</span><span class="sxs-lookup"><span data-stu-id="d578a-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d578a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d578a-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="d578a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d578a-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="d578a-106">[in] La identidad del ensamblado que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="d578a-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="d578a-107">[in] La nueva identidad del ensamblado modificado.</span><span class="sxs-lookup"><span data-stu-id="d578a-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="d578a-108">[in] Un puntero a un búfer que contiene los datos de la directiva de enlace del ensamblado que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="d578a-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="d578a-109">[in] El tamaño de la directiva de enlace que se debe reemplazar.</span><span class="sxs-lookup"><span data-stu-id="d578a-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="d578a-110">[in] Una combinación OR lógica de [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valores, que indica el control de la redirección.</span><span class="sxs-lookup"><span data-stu-id="d578a-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="d578a-111">[out] Un puntero a un búfer que contiene los nuevos datos de la directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="d578a-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="d578a-112">[in, out] Un puntero al tamaño del búfer de nueva directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="d578a-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d578a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d578a-113">Return Value</span></span>  
  
|<span data-ttu-id="d578a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d578a-114">HRESULT</span></span>|<span data-ttu-id="d578a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d578a-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d578a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d578a-116">S_OK</span></span>|<span data-ttu-id="d578a-117">La directiva se modificó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d578a-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="d578a-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d578a-118">E_INVALIDARG</span></span>|<span data-ttu-id="d578a-119">`pwzSourceAssemblyIdentity` o `pwzTargetAssemblyIdentity` era una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="d578a-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="d578a-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d578a-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d578a-121">`pbNewApplicationPolicy` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="d578a-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="d578a-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d578a-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d578a-123">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d578a-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d578a-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d578a-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d578a-125">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d578a-125">The call timed out.</span></span>|  
|<span data-ttu-id="d578a-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d578a-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d578a-127">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d578a-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d578a-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d578a-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d578a-129">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d578a-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d578a-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d578a-130">E_FAIL</span></span>|<span data-ttu-id="d578a-131">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d578a-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d578a-132">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d578a-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d578a-133">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d578a-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d578a-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d578a-134">Remarks</span></span>  
 <span data-ttu-id="d578a-135">El `ModifyApplicationPolicy` método se puede llamar dos veces.</span><span class="sxs-lookup"><span data-stu-id="d578a-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="d578a-136">La primera llamada debe proporcionar un valor null para el `pbNewApplicationPolicy` parámetro.</span><span class="sxs-lookup"><span data-stu-id="d578a-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="d578a-137">Esta llamada devolverá el valor necesario para `pcbNewAppPolicySize`.</span><span class="sxs-lookup"><span data-stu-id="d578a-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="d578a-138">La segunda llamada debe proporcionar este valor para `pcbNewAppPolicySize`y señale a un búfer de ese tamaño para `pbNewApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="d578a-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d578a-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d578a-139">Requirements</span></span>  
 <span data-ttu-id="d578a-140">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d578a-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d578a-141">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d578a-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d578a-142">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d578a-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d578a-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d578a-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d578a-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="d578a-144">See also</span></span>

- [<span data-ttu-id="d578a-145">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d578a-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)

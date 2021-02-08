---
description: 'Más información sobre: ICLRHostBindingPolicyManager:: ModifyApplicationPolicy ((método)'
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
ms.openlocfilehash: 3f7d992f4b7d24233da175814f991106bb97a937
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789936"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="a3849-103">ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="a3849-103">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>

<span data-ttu-id="a3849-104">Modifica la Directiva de enlace para el ensamblado especificado y crea una nueva versión de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="a3849-104">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3849-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3849-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a3849-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3849-106">Parameters</span></span>  

 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="a3849-107">de La identidad del ensamblado que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="a3849-107">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="a3849-108">de Nueva identidad del ensamblado modificado.</span><span class="sxs-lookup"><span data-stu-id="a3849-108">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="a3849-109">de Puntero a un búfer que contiene los datos de la Directiva de enlace del ensamblado que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="a3849-109">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="a3849-110">de Tamaño de la Directiva de enlace que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="a3849-110">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="a3849-111">de Una combinación lógica o lógica de valores de [ehostbindingpolicymodifyflags (](ehostbindingpolicymodifyflags-enumeration.md) , que indica el control de la redirección.</span><span class="sxs-lookup"><span data-stu-id="a3849-111">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="a3849-112">enuncia Un puntero a un búfer que contiene los nuevos datos de la Directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="a3849-112">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="a3849-113">[in, out] Puntero al tamaño del nuevo búfer de directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="a3849-113">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3849-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3849-114">Return Value</span></span>  
  
|<span data-ttu-id="a3849-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3849-115">HRESULT</span></span>|<span data-ttu-id="a3849-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3849-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3849-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3849-117">S_OK</span></span>|<span data-ttu-id="a3849-118">La Directiva se modificó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3849-118">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="a3849-119">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a3849-119">E_INVALIDARG</span></span>|<span data-ttu-id="a3849-120">`pwzSourceAssemblyIdentity` o `pwzTargetAssemblyIdentity` era una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="a3849-120">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="a3849-121">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a3849-121">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a3849-122">`pbNewApplicationPolicy` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="a3849-122">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="a3849-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3849-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3849-124">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3849-124">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3849-125">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3849-125">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3849-126">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a3849-126">The call timed out.</span></span>|  
|<span data-ttu-id="a3849-127">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3849-127">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3849-128">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a3849-128">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3849-129">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3849-129">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3849-130">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a3849-130">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3849-131">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3849-131">E_FAIL</span></span>|<span data-ttu-id="a3849-132">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a3849-132">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3849-133">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a3849-133">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3849-134">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a3849-134">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3849-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3849-135">Remarks</span></span>  

 <span data-ttu-id="a3849-136">`ModifyApplicationPolicy`Se puede llamar al método dos veces.</span><span class="sxs-lookup"><span data-stu-id="a3849-136">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="a3849-137">La primera llamada debe proporcionar un valor null para el `pbNewApplicationPolicy` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a3849-137">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="a3849-138">Esta llamada devolverá con el valor necesario para `pcbNewAppPolicySize` .</span><span class="sxs-lookup"><span data-stu-id="a3849-138">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="a3849-139">La segunda llamada debe proporcionar este valor para `pcbNewAppPolicySize` y apuntar a un búfer de ese tamaño para `pbNewApplicationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="a3849-139">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3849-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3849-140">Requirements</span></span>  

 <span data-ttu-id="a3849-141">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3849-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3849-142">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a3849-142">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3849-143">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3849-143">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3849-144">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3849-144">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3849-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3849-145">See also</span></span>

- [<span data-ttu-id="a3849-146">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3849-146">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)

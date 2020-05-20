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
ms.openlocfilehash: e32714bba2403752f1ac2551ab182f2655f1fa75
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703855"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="004ec-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="004ec-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="004ec-103">Modifica la Directiva de enlace para el ensamblado especificado y crea una nueva versión de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="004ec-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="004ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="004ec-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="004ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="004ec-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="004ec-106">de La identidad del ensamblado que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="004ec-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="004ec-107">de Nueva identidad del ensamblado modificado.</span><span class="sxs-lookup"><span data-stu-id="004ec-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="004ec-108">de Puntero a un búfer que contiene los datos de la Directiva de enlace del ensamblado que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="004ec-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="004ec-109">de Tamaño de la Directiva de enlace que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="004ec-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="004ec-110">de Una combinación lógica o lógica de valores de [ehostbindingpolicymodifyflags (](ehostbindingpolicymodifyflags-enumeration.md) , que indica el control de la redirección.</span><span class="sxs-lookup"><span data-stu-id="004ec-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="004ec-111">enuncia Un puntero a un búfer que contiene los nuevos datos de la Directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="004ec-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="004ec-112">[in, out] Puntero al tamaño del nuevo búfer de directiva de enlace.</span><span class="sxs-lookup"><span data-stu-id="004ec-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="004ec-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="004ec-113">Return Value</span></span>  
  
|<span data-ttu-id="004ec-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="004ec-114">HRESULT</span></span>|<span data-ttu-id="004ec-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="004ec-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="004ec-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="004ec-116">S_OK</span></span>|<span data-ttu-id="004ec-117">La Directiva se modificó correctamente.</span><span class="sxs-lookup"><span data-stu-id="004ec-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="004ec-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="004ec-118">E_INVALIDARG</span></span>|<span data-ttu-id="004ec-119">`pwzSourceAssemblyIdentity`o `pwzTargetAssemblyIdentity` era una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="004ec-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="004ec-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="004ec-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="004ec-121">`pbNewApplicationPolicy` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="004ec-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="004ec-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="004ec-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="004ec-123">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="004ec-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="004ec-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="004ec-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="004ec-125">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="004ec-125">The call timed out.</span></span>|  
|<span data-ttu-id="004ec-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="004ec-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="004ec-127">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="004ec-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="004ec-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="004ec-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="004ec-129">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="004ec-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="004ec-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="004ec-130">E_FAIL</span></span>|<span data-ttu-id="004ec-131">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="004ec-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="004ec-132">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="004ec-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="004ec-133">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="004ec-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="004ec-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="004ec-134">Remarks</span></span>  
 <span data-ttu-id="004ec-135">`ModifyApplicationPolicy`Se puede llamar al método dos veces.</span><span class="sxs-lookup"><span data-stu-id="004ec-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="004ec-136">La primera llamada debe proporcionar un valor null para el `pbNewApplicationPolicy` parámetro.</span><span class="sxs-lookup"><span data-stu-id="004ec-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="004ec-137">Esta llamada devolverá con el valor necesario para `pcbNewAppPolicySize` .</span><span class="sxs-lookup"><span data-stu-id="004ec-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="004ec-138">La segunda llamada debe proporcionar este valor para `pcbNewAppPolicySize` y apuntar a un búfer de ese tamaño para `pbNewApplicationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="004ec-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="004ec-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="004ec-139">Requirements</span></span>  
 <span data-ttu-id="004ec-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="004ec-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="004ec-141">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="004ec-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="004ec-142">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="004ec-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="004ec-143">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="004ec-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004ec-144">Consulta también</span><span class="sxs-lookup"><span data-stu-id="004ec-144">See also</span></span>

- [<span data-ttu-id="004ec-145">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="004ec-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)

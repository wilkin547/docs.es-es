---
description: 'Más información sobre: ICLRAssemblyIdentityManager:: Getbindingidentityfromfile ((método)'
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 82e72155b38f71fe2c024994f07178638095be9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689555"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="9a19c-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="9a19c-103">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>

<span data-ttu-id="9a19c-104">Obtiene los datos de enlace de identidad del ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="9a19c-104">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a19c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a19c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a19c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a19c-106">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="9a19c-107">de Ruta de acceso al archivo que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="9a19c-107">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9a19c-108">de Un valor de la enumeración [eclrassemblyidentityflags (](eclrassemblyidentityflags-enumeration.md) que indica el tipo de identidad de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9a19c-108">[in] A value of the [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="9a19c-109">Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="9a19c-109">Provided for future extensibility.</span></span> <span data-ttu-id="9a19c-110">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión 2,0 de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9a19c-110">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="9a19c-111">enuncia Búfer que contiene los datos de identidad del ensamblado opaco.</span><span class="sxs-lookup"><span data-stu-id="9a19c-111">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="9a19c-112">[in, out] Puntero al tamaño de `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="9a19c-112">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a19c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a19c-113">Return Value</span></span>  
  
|<span data-ttu-id="9a19c-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a19c-114">HRESULT</span></span>|<span data-ttu-id="9a19c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a19c-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a19c-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a19c-116">S_OK</span></span>|<span data-ttu-id="9a19c-117">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a19c-117">The method returned successfully.</span></span>|  
|<span data-ttu-id="9a19c-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9a19c-118">E_INVALIDARG</span></span>|<span data-ttu-id="9a19c-119">El valor de proporcionado `pwzFilePath` es NULL.</span><span class="sxs-lookup"><span data-stu-id="9a19c-119">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="9a19c-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9a19c-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9a19c-121">El tamaño de `pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="9a19c-121">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="9a19c-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a19c-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a19c-123">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a19c-123">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a19c-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a19c-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a19c-125">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9a19c-125">The call timed out.</span></span>|  
|<span data-ttu-id="9a19c-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a19c-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a19c-127">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9a19c-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a19c-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a19c-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a19c-129">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="9a19c-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a19c-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a19c-130">E_FAIL</span></span>|<span data-ttu-id="9a19c-131">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="9a19c-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a19c-132">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9a19c-132">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a19c-133">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9a19c-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a19c-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9a19c-134">Remarks</span></span>  

 <span data-ttu-id="9a19c-135">`GetBindingIdentityFromFile` normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="9a19c-135">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="9a19c-136">La primera llamada proporciona un valor null para `pwzBuffer` y el método devuelve el tamaño adecuado en `pcchBufferSize` .</span><span class="sxs-lookup"><span data-stu-id="9a19c-136">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="9a19c-137">La segunda llamada proporciona un búfer asignado adecuadamente y el método devuelve con los datos de búfer reales al finalizar.</span><span class="sxs-lookup"><span data-stu-id="9a19c-137">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a19c-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a19c-138">Requirements</span></span>  

 <span data-ttu-id="9a19c-139">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a19c-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a19c-140">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9a19c-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a19c-141">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a19c-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a19c-142">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a19c-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a19c-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a19c-143">See also</span></span>

- [<span data-ttu-id="9a19c-144">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a19c-144">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9a19c-145">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a19c-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9a19c-146">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a19c-146">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)

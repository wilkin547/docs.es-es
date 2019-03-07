---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b094c37368e3b6515518d94fbdbf5033ec74b90f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484724"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="a3f99-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="a3f99-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="a3f99-103">Obtiene la identidad del ensamblado enlace de datos para el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="a3f99-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3f99-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3f99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3f99-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="a3f99-106">[in] La ruta de acceso al archivo que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="a3f99-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a3f99-107">[in] Un valor de la [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeración que indica el tipo de identidad de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a3f99-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="a3f99-108">Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="a3f99-108">Provided for future extensibility.</span></span> <span data-ttu-id="a3f99-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que es compatible con common language runtime (CLR) versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="a3f99-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="a3f99-110">[out] Un búfer que contiene los datos de identidad de ensamblado opaco.</span><span class="sxs-lookup"><span data-stu-id="a3f99-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="a3f99-111">[in, out] Un puntero al tamaño de `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="a3f99-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3f99-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3f99-112">Return Value</span></span>  
  
|<span data-ttu-id="a3f99-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3f99-113">HRESULT</span></span>|<span data-ttu-id="a3f99-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3f99-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3f99-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3f99-115">S_OK</span></span>|<span data-ttu-id="a3f99-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3f99-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="a3f99-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a3f99-117">E_INVALIDARG</span></span>|<span data-ttu-id="a3f99-118">Suministrado `pwzFilePath` es null.</span><span class="sxs-lookup"><span data-stu-id="a3f99-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="a3f99-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a3f99-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a3f99-120">El tamaño de `pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="a3f99-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="a3f99-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3f99-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3f99-122">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3f99-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3f99-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3f99-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3f99-124">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a3f99-124">The call timed out.</span></span>|  
|<span data-ttu-id="a3f99-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3f99-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3f99-126">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a3f99-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3f99-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3f99-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3f99-128">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a3f99-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3f99-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3f99-129">E_FAIL</span></span>|<span data-ttu-id="a3f99-130">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a3f99-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3f99-131">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a3f99-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3f99-132">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a3f99-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f99-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3f99-133">Remarks</span></span>  
 <span data-ttu-id="a3f99-134">`GetBindingIdentityFromFile` Normalmente, se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="a3f99-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="a3f99-135">La primera llamada proporciona un valor null para `pwzBuffer`, y el método devuelve el tamaño adecuado en `pcchBufferSize`.</span><span class="sxs-lookup"><span data-stu-id="a3f99-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="a3f99-136">La segunda llamada proporciona un búfer asignado correctamente, y el método devuelve con los datos de búfer real tras la finalización.</span><span class="sxs-lookup"><span data-stu-id="a3f99-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f99-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3f99-137">Requirements</span></span>  
 <span data-ttu-id="a3f99-138">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f99-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f99-139">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a3f99-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3f99-140">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3f99-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f99-141">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f99-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f99-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3f99-142">See also</span></span>
- [<span data-ttu-id="a3f99-143">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f99-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a3f99-144">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f99-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a3f99-145">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f99-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)

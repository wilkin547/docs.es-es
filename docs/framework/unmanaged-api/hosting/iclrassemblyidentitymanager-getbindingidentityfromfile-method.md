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
ms.openlocfilehash: 443acfa77dc8103008263f19bed116d02e7ea676
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716751"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="a9fc6-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="a9fc6-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>

<span data-ttu-id="a9fc6-103">Obtiene los datos de enlace de identidad del ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9fc6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9fc6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9fc6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9fc6-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="a9fc6-106">de Ruta de acceso al archivo que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a9fc6-107">de Un valor de la enumeración [eclrassemblyidentityflags (](eclrassemblyidentityflags-enumeration.md) que indica el tipo de identidad de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-107">[in] A value of the [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="a9fc6-108">Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-108">Provided for future extensibility.</span></span> <span data-ttu-id="a9fc6-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión 2,0 de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a9fc6-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="a9fc6-110">enuncia Búfer que contiene los datos de identidad del ensamblado opaco.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="a9fc6-111">[in, out] Puntero al tamaño de `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="a9fc6-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9fc6-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9fc6-112">Return Value</span></span>  
  
|<span data-ttu-id="a9fc6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9fc6-113">HRESULT</span></span>|<span data-ttu-id="a9fc6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9fc6-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9fc6-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9fc6-115">S_OK</span></span>|<span data-ttu-id="a9fc6-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="a9fc6-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a9fc6-117">E_INVALIDARG</span></span>|<span data-ttu-id="a9fc6-118">El valor de proporcionado `pwzFilePath` es NULL.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="a9fc6-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a9fc6-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a9fc6-120">El tamaño de `pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="a9fc6-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9fc6-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9fc6-122">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9fc6-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9fc6-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9fc6-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-124">The call timed out.</span></span>|  
|<span data-ttu-id="a9fc6-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9fc6-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9fc6-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9fc6-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9fc6-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9fc6-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9fc6-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9fc6-129">E_FAIL</span></span>|<span data-ttu-id="a9fc6-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9fc6-131">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9fc6-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9fc6-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9fc6-133">Remarks</span></span>  

 <span data-ttu-id="a9fc6-134">`GetBindingIdentityFromFile` normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="a9fc6-135">La primera llamada proporciona un valor null para `pwzBuffer` y el método devuelve el tamaño adecuado en `pcchBufferSize` .</span><span class="sxs-lookup"><span data-stu-id="a9fc6-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="a9fc6-136">La segunda llamada proporciona un búfer asignado adecuadamente y el método devuelve con los datos de búfer reales al finalizar.</span><span class="sxs-lookup"><span data-stu-id="a9fc6-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9fc6-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9fc6-137">Requirements</span></span>  

 <span data-ttu-id="a9fc6-138">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9fc6-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9fc6-139">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a9fc6-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9fc6-140">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9fc6-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9fc6-141">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9fc6-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fc6-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9fc6-142">See also</span></span>

- [<span data-ttu-id="a9fc6-143">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9fc6-143">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a9fc6-144">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9fc6-144">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a9fc6-145">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9fc6-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)

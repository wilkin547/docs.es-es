---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55f3bd89f0ca177bcd4edef2e17a7d2256a0042a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773493"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="c8ae8-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference (Método)</span><span class="sxs-lookup"><span data-stu-id="c8ae8-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="c8ae8-103">Obtiene un [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerador para las identidades de ensamblado al que hace referencia el ensamblado con el tipo de identidad especificado.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8ae8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8ae8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8ae8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8ae8-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="c8ae8-106">[in] Un valor válido que especifica la arquitectura del procesador, tal como se define en WinNT.h.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c8ae8-107">[in] Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="c8ae8-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor compatible con la versión actual de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c8ae8-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="c8ae8-109">[in] Una identidad de enlace de ensamblado opaco, normalmente se devuelven de una llamada a la [GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) o [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="c8ae8-110">[out] Un puntero de interfaz a un `ICLRProbingAssemblyEnum` enumerador que contiene referencias a los ensamblados al que hace referencia el ensamblado identificado por `pwzReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8ae8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c8ae8-111">Return Value</span></span>  
  
|<span data-ttu-id="c8ae8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8ae8-112">HRESULT</span></span>|<span data-ttu-id="c8ae8-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c8ae8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8ae8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8ae8-114">S_OK</span></span>|<span data-ttu-id="c8ae8-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="c8ae8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8ae8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8ae8-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8ae8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8ae8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8ae8-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-119">The call timed out.</span></span>|  
|<span data-ttu-id="c8ae8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8ae8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8ae8-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8ae8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8ae8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8ae8-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8ae8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8ae8-124">E_FAIL</span></span>|<span data-ttu-id="c8ae8-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8ae8-126">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8ae8-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c8ae8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8ae8-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8ae8-128">Requirements</span></span>  
 <span data-ttu-id="c8ae8-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8ae8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8ae8-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8ae8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8ae8-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8ae8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8ae8-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8ae8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ae8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8ae8-133">See also</span></span>

- [<span data-ttu-id="c8ae8-134">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8ae8-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c8ae8-135">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8ae8-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c8ae8-136">ICLRProbingAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8ae8-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)

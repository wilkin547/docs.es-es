---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
ms.openlocfilehash: f4c200ad23ff7a71298e84fda857912da53978a5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126692"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="af3d0-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="af3d0-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="af3d0-103">Obtiene un puntero a un objeto [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="af3d0-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af3d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af3d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af3d0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af3d0-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="af3d0-106">de Puntero de interfaz a un `IStream` que contiene el ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="af3d0-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="af3d0-107">de Se proporciona para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="af3d0-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="af3d0-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="af3d0-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="af3d0-109">de Un puntero a un objeto [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que contiene datos de identidad del ensamblado para los ensamblados que se van a excluir de `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="af3d0-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="af3d0-110">enuncia Puntero a la dirección de un objeto `ICLRReferenceAssemblyEnum` que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en `pStream`, excluyendo los ensamblados en `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="af3d0-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af3d0-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af3d0-111">Return Value</span></span>  
  
|<span data-ttu-id="af3d0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af3d0-112">HRESULT</span></span>|<span data-ttu-id="af3d0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="af3d0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af3d0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="af3d0-114">S_OK</span></span>|<span data-ttu-id="af3d0-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="af3d0-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="af3d0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="af3d0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="af3d0-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="af3d0-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="af3d0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="af3d0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="af3d0-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="af3d0-119">The call timed out.</span></span>|  
|<span data-ttu-id="af3d0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="af3d0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="af3d0-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="af3d0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="af3d0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="af3d0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="af3d0-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="af3d0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="af3d0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="af3d0-124">E_FAIL</span></span>|<span data-ttu-id="af3d0-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="af3d0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="af3d0-126">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="af3d0-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="af3d0-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="af3d0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af3d0-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af3d0-128">Remarks</span></span>  
 <span data-ttu-id="af3d0-129">El autor de la llamada puede optar por excluir un conjunto de referencias de ensamblado conocidas de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="af3d0-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="af3d0-130">Este conjunto se define mediante `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="af3d0-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af3d0-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af3d0-131">Requirements</span></span>  
 <span data-ttu-id="af3d0-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af3d0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af3d0-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="af3d0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af3d0-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="af3d0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af3d0-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af3d0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3d0-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="af3d0-136">See also</span></span>

- [<span data-ttu-id="af3d0-137">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af3d0-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="af3d0-138">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af3d0-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="af3d0-139">ICLRReferenceAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af3d0-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)

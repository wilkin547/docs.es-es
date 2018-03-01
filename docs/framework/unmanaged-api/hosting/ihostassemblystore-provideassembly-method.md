---
title: "IHostAssemblyStore::ProvideAssembly (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2097c1ea64e5e9a2a09e0ec57243624b05eeea65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="d8f0c-102">IHostAssemblyStore::ProvideAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d8f0c-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="d8f0c-103">Obtiene una referencia a un ensamblado que no hace referencia la [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que se devuelve de [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="d8f0c-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="d8f0c-104">Common language runtime (CLR) llama `ProvideAssembly` para cada ensamblado que no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8f0c-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8f0c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8f0c-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="d8f0c-107">[in] Un puntero a un [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instancia que usa el host para determinar ciertas características del enlace, incluida la presencia o ausencia de directivas de control de versiones así como para enlazar con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="d8f0c-108">[out] Un puntero a un identificador único para el ensamblado solicitado para esta `IStream`.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="d8f0c-109">[out] Llamada de invocación de un puntero a datos específicos del host que se utilizan para determinar la evidencia del ensamblado solicitado sin necesidad de una plataforma.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="d8f0c-110">`pHostContext`corresponde a la <xref:System.Reflection.Assembly.HostContext%2A> propiedad de los recursos administrados <xref:System.Reflection.Assembly> clase.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="d8f0c-111">[out] Un puntero a la dirección de un `IStream` que contiene la imagen ejecutable portable (PE) para cargar, o null si no se pudo encontrar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="d8f0c-112">[out] Un puntero a la dirección de un `IStream` que contiene la información de depuración (PDB) del programa, o null si no se encontró el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8f0c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8f0c-113">Return Value</span></span>  
  
|<span data-ttu-id="d8f0c-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8f0c-114">HRESULT</span></span>|<span data-ttu-id="d8f0c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8f0c-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8f0c-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8f0c-116">S_OK</span></span>|<span data-ttu-id="d8f0c-117">`ProvideAssembly`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="d8f0c-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8f0c-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8f0c-119">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8f0c-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8f0c-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8f0c-121">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-121">The call timed out.</span></span>|  
|<span data-ttu-id="d8f0c-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8f0c-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8f0c-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8f0c-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8f0c-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8f0c-125">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8f0c-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8f0c-126">E_FAIL</span></span>|<span data-ttu-id="d8f0c-127">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8f0c-128">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8f0c-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d8f0c-130">COR_E_FILENOTFOUND (0 X 80070002)</span><span class="sxs-lookup"><span data-stu-id="d8f0c-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="d8f0c-131">No se pudo encontrar el ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="d8f0c-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d8f0c-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d8f0c-133">El tamaño de búfer especificado por `pAssemblyId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8f0c-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8f0c-134">Remarks</span></span>  
 <span data-ttu-id="d8f0c-135">Devuelve el valor de identidad para `pAssemblyId` especificado por el host.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="d8f0c-136">Identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="d8f0c-137">CLR utiliza este valor como un identificador único para la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="d8f0c-138">Comprueba cada valor con los valores para `pAssemblyId` devueltos por otras llamadas a `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="d8f0c-139">Si el host devuelve el mismo `pAssemblyId` valor por otro `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="d8f0c-140">Si es así, el tiempo de ejecución carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="d8f0c-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f0c-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8f0c-141">Requirements</span></span>  
 <span data-ttu-id="d8f0c-142">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8f0c-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f0c-143">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8f0c-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8f0c-144">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8f0c-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8f0c-145">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f0c-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f0c-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8f0c-146">See Also</span></span>  
 [<span data-ttu-id="d8f0c-147">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8f0c-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="d8f0c-148">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8f0c-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="d8f0c-149">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8f0c-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

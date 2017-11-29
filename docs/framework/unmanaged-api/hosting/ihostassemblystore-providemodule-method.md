---
title: "IHostAssemblyStore::ProvideModule (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6894d15221b8ace12e76b8eba4ac69503eaa792d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="40507-102">IHostAssemblyStore::ProvideModule (Método)</span><span class="sxs-lookup"><span data-stu-id="40507-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="40507-103">Resuelve un módulo dentro de un ensamblado o vinculado (pero no incrustado) del archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="40507-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40507-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40507-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40507-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40507-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="40507-106">[in] Un puntero a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instancia que describe el módulo solicitado <xref:System.AppDomain>, ensamblado y nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="40507-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="40507-107">[out] Un puntero a un identificador único para el `IStream` que contiene el módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="40507-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="40507-108">[out] Un puntero a la dirección de un `IStream` de objeto, que contiene la imagen ejecutable portable (PE) que va a cargar, o null si no se encontró el módulo.</span><span class="sxs-lookup"><span data-stu-id="40507-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="40507-109">[out] Un puntero a la dirección de un `IStream` de objeto, que contiene la información de depuración (PDB) del programa para el módulo solicitado, o null si no se encontró el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="40507-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40507-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="40507-110">Return Value</span></span>  
  
|<span data-ttu-id="40507-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40507-111">HRESULT</span></span>|<span data-ttu-id="40507-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="40507-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40507-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="40507-113">S_OK</span></span>|<span data-ttu-id="40507-114">`ProvideModule`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="40507-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="40507-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40507-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40507-116">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="40507-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40507-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40507-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40507-118">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="40507-118">The call timed out.</span></span>|  
|<span data-ttu-id="40507-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40507-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40507-120">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="40507-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40507-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40507-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40507-122">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="40507-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40507-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40507-123">E_FAIL</span></span>|<span data-ttu-id="40507-124">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="40507-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40507-125">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="40507-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40507-126">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="40507-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="40507-127">COR_E_FILENOTFOUND (0 X 80070002)</span><span class="sxs-lookup"><span data-stu-id="40507-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="40507-128">No se encuentra el ensamblado solicitado o el recurso vinculado.</span><span class="sxs-lookup"><span data-stu-id="40507-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="40507-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="40507-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="40507-130">`pdwModuleId`no es lo suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="40507-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40507-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40507-131">Remarks</span></span>  
 <span data-ttu-id="40507-132">Devuelve el valor de identidad para `pdwModuleId` especificado por el host.</span><span class="sxs-lookup"><span data-stu-id="40507-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="40507-133">Identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="40507-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="40507-134">El CLR usa este valor como identificador único para la secuencia asociada.</span><span class="sxs-lookup"><span data-stu-id="40507-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="40507-135">Comprueba cada valor con los valores para `pAssemblyId` devueltos por llamadas a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) y con los valores de `pdwModuleId` devueltos por otras llamadas a `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="40507-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="40507-136">Si el host devuelve el mismo valor de identificador para otro `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia.</span><span class="sxs-lookup"><span data-stu-id="40507-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="40507-137">Si es así, el CLR carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="40507-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="40507-138">Por lo tanto, el identificador también no debe solaparse con los identificadores de ensamblado devueltos por `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="40507-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40507-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40507-139">Requirements</span></span>  
 <span data-ttu-id="40507-140">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40507-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40507-141">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40507-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40507-142">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40507-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40507-143">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40507-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40507-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="40507-144">See Also</span></span>  
 [<span data-ttu-id="40507-145">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40507-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="40507-146">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40507-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="40507-147">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40507-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

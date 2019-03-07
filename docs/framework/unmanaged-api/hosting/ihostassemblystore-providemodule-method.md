---
title: IHostAssemblyStore::ProvideModule (Método)
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1d61e7495a3d95b5326e5051775e23e19cb1b45
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503091"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="ad27c-102">IHostAssemblyStore::ProvideModule (Método)</span><span class="sxs-lookup"><span data-stu-id="ad27c-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="ad27c-103">Se resuelve como un archivo de recursos de módulo dentro de un ensamblado o vinculado (pero no incrustado).</span><span class="sxs-lookup"><span data-stu-id="ad27c-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad27c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad27c-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad27c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad27c-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="ad27c-106">[in] Un puntero a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instancia que describe el módulo solicitado <xref:System.AppDomain>, ensamblado y el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="ad27c-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="ad27c-107">[out] Un puntero a un identificador único para el `IStream` que contiene el módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="ad27c-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="ad27c-108">[out] Un puntero a la dirección de un `IStream` de objeto, que contiene la imagen ejecutable portable (PE) que va a cargar, o null si no se pudo encontrar el módulo.</span><span class="sxs-lookup"><span data-stu-id="ad27c-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="ad27c-109">[out] Un puntero a la dirección de un `IStream` de objeto, que contiene la información de depuración (PDB) de programa para el módulo solicitado, o null si no se encontró el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="ad27c-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad27c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ad27c-110">Return Value</span></span>  
  
|<span data-ttu-id="ad27c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad27c-111">HRESULT</span></span>|<span data-ttu-id="ad27c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad27c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad27c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad27c-113">S_OK</span></span>|<span data-ttu-id="ad27c-114">`ProvideModule` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad27c-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="ad27c-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ad27c-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ad27c-116">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad27c-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ad27c-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ad27c-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ad27c-118">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ad27c-118">The call timed out.</span></span>|  
|<span data-ttu-id="ad27c-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ad27c-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ad27c-120">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ad27c-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ad27c-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ad27c-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ad27c-122">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ad27c-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ad27c-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ad27c-123">E_FAIL</span></span>|<span data-ttu-id="ad27c-124">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ad27c-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ad27c-125">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ad27c-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ad27c-126">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ad27c-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ad27c-127">COR_E_FILENOTFOUND (0 X 80070002)</span><span class="sxs-lookup"><span data-stu-id="ad27c-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="ad27c-128">No se pudo encontrar el ensamblado solicitado o el recurso vinculado.</span><span class="sxs-lookup"><span data-stu-id="ad27c-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="ad27c-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ad27c-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ad27c-130">`pdwModuleId` no es suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="ad27c-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad27c-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad27c-131">Remarks</span></span>  
 <span data-ttu-id="ad27c-132">Devuelve el valor de identidad para `pdwModuleId` especificado por el host.</span><span class="sxs-lookup"><span data-stu-id="ad27c-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="ad27c-133">Identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="ad27c-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="ad27c-134">CLR usa este valor como identificador único para la secuencia asociada.</span><span class="sxs-lookup"><span data-stu-id="ad27c-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="ad27c-135">Comprueba cada valor con los valores de `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) y con los valores de `pdwModuleId` devueltos por otras llamadas a `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="ad27c-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="ad27c-136">Si el host devuelve el mismo valor de identificador para otra `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia.</span><span class="sxs-lookup"><span data-stu-id="ad27c-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="ad27c-137">Si es así, el CLR carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="ad27c-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="ad27c-138">Por lo tanto, el identificador también no debe solaparse con los identificadores del ensamblado devuelto desde `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="ad27c-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad27c-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad27c-139">Requirements</span></span>  
 <span data-ttu-id="ad27c-140">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad27c-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad27c-141">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ad27c-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad27c-142">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad27c-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad27c-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad27c-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad27c-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad27c-144">See also</span></span>
- [<span data-ttu-id="ad27c-145">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad27c-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ad27c-146">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad27c-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="ad27c-147">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad27c-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

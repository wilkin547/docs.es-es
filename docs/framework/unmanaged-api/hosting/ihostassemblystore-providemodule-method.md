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
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078343"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="fee44-102">IHostAssemblyStore::ProvideModule (Método)</span><span class="sxs-lookup"><span data-stu-id="fee44-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="fee44-103">Se resuelve como un archivo de recursos de módulo dentro de un ensamblado o vinculado (pero no incrustado).</span><span class="sxs-lookup"><span data-stu-id="fee44-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fee44-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fee44-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fee44-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fee44-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="fee44-106">[in] Un puntero a un [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instancia que describe el módulo solicitado <xref:System.AppDomain>, ensamblado y el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="fee44-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="fee44-107">[out] Un puntero a un identificador único para el `IStream` que contiene el módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="fee44-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="fee44-108">[out] Un puntero a la dirección de un `IStream` de objeto, que contiene la imagen ejecutable portable (PE) que va a cargar, o null si no se pudo encontrar el módulo.</span><span class="sxs-lookup"><span data-stu-id="fee44-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="fee44-109">[out] Un puntero a la dirección de un `IStream` de objeto, que contiene la información de depuración (PDB) de programa para el módulo solicitado, o null si no se encontró el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="fee44-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fee44-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fee44-110">Return Value</span></span>  
  
|<span data-ttu-id="fee44-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fee44-111">HRESULT</span></span>|<span data-ttu-id="fee44-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fee44-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fee44-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fee44-113">S_OK</span></span>|`ProvideModule` <span data-ttu-id="fee44-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fee44-114">returned successfully.</span></span>|  
|<span data-ttu-id="fee44-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fee44-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fee44-116">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fee44-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fee44-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fee44-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fee44-118">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fee44-118">The call timed out.</span></span>|  
|<span data-ttu-id="fee44-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fee44-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fee44-120">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fee44-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fee44-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fee44-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fee44-122">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="fee44-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fee44-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fee44-123">E_FAIL</span></span>|<span data-ttu-id="fee44-124">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="fee44-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fee44-125">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="fee44-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fee44-126">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fee44-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fee44-127">COR_E_FILENOTFOUND (0 X 80070002)</span><span class="sxs-lookup"><span data-stu-id="fee44-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="fee44-128">No se pudo encontrar el ensamblado solicitado o el recurso vinculado.</span><span class="sxs-lookup"><span data-stu-id="fee44-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="fee44-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="fee44-129">E_NOT_SUFFICIENT_BUFFER</span></span>|`pdwModuleId` <span data-ttu-id="fee44-130">no es suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="fee44-130">is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fee44-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fee44-131">Remarks</span></span>  
 <span data-ttu-id="fee44-132">Devuelve el valor de identidad para `pdwModuleId` especificado por el host.</span><span class="sxs-lookup"><span data-stu-id="fee44-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="fee44-133">Identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="fee44-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="fee44-134">CLR usa este valor como identificador único para la secuencia asociada.</span><span class="sxs-lookup"><span data-stu-id="fee44-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="fee44-135">Comprueba cada valor con los valores de `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) y con los valores de `pdwModuleId` devueltos por otras llamadas a `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="fee44-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="fee44-136">Si el host devuelve el mismo valor de identificador para otra `IStream`, CLR comprueba si ya se ha asignado el contenido de esa secuencia.</span><span class="sxs-lookup"><span data-stu-id="fee44-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="fee44-137">Si es así, el CLR carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="fee44-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="fee44-138">Por lo tanto, el identificador también no debe solaparse con los identificadores del ensamblado devuelto desde `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="fee44-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fee44-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fee44-139">Requirements</span></span>  
 <span data-ttu-id="fee44-140">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fee44-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fee44-141">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fee44-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fee44-142">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fee44-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fee44-143">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fee44-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fee44-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="fee44-144">See also</span></span>

- [<span data-ttu-id="fee44-145">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fee44-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="fee44-146">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fee44-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="fee44-147">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fee44-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

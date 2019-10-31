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
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124471"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="87b45-102">IHostAssemblyStore::ProvideModule (Método)</span><span class="sxs-lookup"><span data-stu-id="87b45-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="87b45-103">Resuelve un módulo dentro de un ensamblado o un archivo de recursos vinculado (pero no incrustado).</span><span class="sxs-lookup"><span data-stu-id="87b45-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87b45-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87b45-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87b45-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="87b45-106">de Un puntero a una instancia de [modulebindinfo (](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) que describe el <xref:System.AppDomain>, el ensamblado y el nombre del módulo solicitados.</span><span class="sxs-lookup"><span data-stu-id="87b45-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="87b45-107">enuncia Un puntero a un identificador único para el `IStream` que contiene el módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="87b45-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="87b45-108">enuncia Puntero a la dirección de un objeto `IStream`, que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se encuentra el módulo.</span><span class="sxs-lookup"><span data-stu-id="87b45-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="87b45-109">enuncia Puntero a la dirección de un objeto `IStream`, que contiene la información de depuración del programa (PDB) para el módulo solicitado, o null si no se encuentra el archivo. pdb.</span><span class="sxs-lookup"><span data-stu-id="87b45-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87b45-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87b45-110">Return Value</span></span>  
  
|<span data-ttu-id="87b45-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87b45-111">HRESULT</span></span>|<span data-ttu-id="87b45-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="87b45-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87b45-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="87b45-113">S_OK</span></span>|<span data-ttu-id="87b45-114">`ProvideModule` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="87b45-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="87b45-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87b45-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87b45-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="87b45-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87b45-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87b45-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87b45-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="87b45-118">The call timed out.</span></span>|  
|<span data-ttu-id="87b45-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87b45-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87b45-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="87b45-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87b45-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87b45-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87b45-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="87b45-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87b45-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87b45-123">E_FAIL</span></span>|<span data-ttu-id="87b45-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="87b45-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87b45-125">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="87b45-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87b45-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87b45-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87b45-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="87b45-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="87b45-128">No se encontró el ensamblado o el recurso vinculado solicitado.</span><span class="sxs-lookup"><span data-stu-id="87b45-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="87b45-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="87b45-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="87b45-130">`pdwModuleId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="87b45-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87b45-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87b45-131">Remarks</span></span>  
 <span data-ttu-id="87b45-132">El host especifica el valor de identidad devuelto para `pdwModuleId`.</span><span class="sxs-lookup"><span data-stu-id="87b45-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="87b45-133">Los identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="87b45-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="87b45-134">CLR usa este valor como identificador único para la secuencia asociada.</span><span class="sxs-lookup"><span data-stu-id="87b45-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="87b45-135">Comprueba cada valor con los valores de `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) y con los valores de `pdwModuleId` devueltos por otras llamadas a `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="87b45-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="87b45-136">Si el host devuelve el mismo valor de identificador para otro `IStream`, CLR comprueba si ya se ha asignado el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="87b45-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="87b45-137">Si es así, CLR carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="87b45-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="87b45-138">Por lo tanto, el identificador tampoco debe superponerse con los identificadores de ensamblado devueltos por `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="87b45-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b45-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87b45-139">Requirements</span></span>  
 <span data-ttu-id="87b45-140">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87b45-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b45-141">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="87b45-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87b45-142">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="87b45-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87b45-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b45-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b45-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="87b45-144">See also</span></span>

- [<span data-ttu-id="87b45-145">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87b45-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="87b45-146">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87b45-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="87b45-147">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87b45-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)

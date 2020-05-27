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
ms.openlocfilehash: 002f4177f19c2aae99e91e3fe1029b81e17481dc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805015"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="47c94-102">IHostAssemblyStore::ProvideModule (Método)</span><span class="sxs-lookup"><span data-stu-id="47c94-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="47c94-103">Resuelve un módulo dentro de un ensamblado o un archivo de recursos vinculado (pero no incrustado).</span><span class="sxs-lookup"><span data-stu-id="47c94-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47c94-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47c94-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47c94-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="47c94-106">de Puntero a una instancia de [modulebindinfo (](modulebindinfo-structure.md) que describe el <xref:System.AppDomain> ensamblado, el ensamblado y el nombre del módulo solicitados.</span><span class="sxs-lookup"><span data-stu-id="47c94-106">[in] A pointer to a [ModuleBindInfo](modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="47c94-107">enuncia Un puntero a un identificador único para `IStream` que contiene el módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="47c94-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="47c94-108">enuncia Un puntero a la dirección de un `IStream` objeto, que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se encuentra el módulo.</span><span class="sxs-lookup"><span data-stu-id="47c94-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="47c94-109">enuncia Puntero a la dirección de un `IStream` objeto, que contiene la información de depuración del programa (PDB) para el módulo solicitado, o null si no se encuentra el archivo. pdb.</span><span class="sxs-lookup"><span data-stu-id="47c94-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47c94-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47c94-110">Return Value</span></span>  
  
|<span data-ttu-id="47c94-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47c94-111">HRESULT</span></span>|<span data-ttu-id="47c94-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="47c94-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47c94-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="47c94-113">S_OK</span></span>|<span data-ttu-id="47c94-114">`ProvideModule`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="47c94-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="47c94-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47c94-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47c94-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="47c94-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47c94-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47c94-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47c94-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="47c94-118">The call timed out.</span></span>|  
|<span data-ttu-id="47c94-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47c94-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47c94-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="47c94-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47c94-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47c94-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47c94-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="47c94-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47c94-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47c94-123">E_FAIL</span></span>|<span data-ttu-id="47c94-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="47c94-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47c94-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="47c94-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47c94-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="47c94-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="47c94-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="47c94-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="47c94-128">No se encontró el ensamblado o el recurso vinculado solicitado.</span><span class="sxs-lookup"><span data-stu-id="47c94-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="47c94-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="47c94-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="47c94-130">`pdwModuleId`no es lo suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="47c94-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47c94-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47c94-131">Remarks</span></span>  
 <span data-ttu-id="47c94-132">El valor de identidad devuelto por `pdwModuleId` se especifica mediante el host.</span><span class="sxs-lookup"><span data-stu-id="47c94-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="47c94-133">Los identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="47c94-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="47c94-134">CLR usa este valor como identificador único para la secuencia asociada.</span><span class="sxs-lookup"><span data-stu-id="47c94-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="47c94-135">Comprueba cada valor con los valores `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](ihostassemblystore-provideassembly-method.md) y con los valores `pdwModuleId` devueltos por otras llamadas a `ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="47c94-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="47c94-136">Si el host devuelve el mismo valor de identificador para otro `IStream` , CLR comprueba si ya se ha asignado el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="47c94-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="47c94-137">Si es así, CLR carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="47c94-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="47c94-138">Por lo tanto, el identificador tampoco debe superponerse con los identificadores de ensamblado devueltos por `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="47c94-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c94-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47c94-139">Requirements</span></span>  
 <span data-ttu-id="47c94-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47c94-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c94-141">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="47c94-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47c94-142">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="47c94-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47c94-143">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c94-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c94-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47c94-144">See also</span></span>

- [<span data-ttu-id="47c94-145">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47c94-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="47c94-146">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47c94-146">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="47c94-147">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47c94-147">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

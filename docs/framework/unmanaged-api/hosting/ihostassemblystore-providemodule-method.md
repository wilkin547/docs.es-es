---
description: 'Más información acerca de: IHostAssemblyStore::P método rovideModule'
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
ms.openlocfilehash: 9e783b9f8db303d095995507689d7567225a51fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709033"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="7452a-103">IHostAssemblyStore::ProvideModule (Método)</span><span class="sxs-lookup"><span data-stu-id="7452a-103">IHostAssemblyStore::ProvideModule Method</span></span>

<span data-ttu-id="7452a-104">Resuelve un módulo dentro de un ensamblado o un archivo de recursos vinculado (pero no incrustado).</span><span class="sxs-lookup"><span data-stu-id="7452a-104">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7452a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7452a-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7452a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7452a-106">Parameters</span></span>  

 `pBindInfo`  
 <span data-ttu-id="7452a-107">de Puntero a una instancia de [modulebindinfo (](modulebindinfo-structure.md) que describe el <xref:System.AppDomain> ensamblado, el ensamblado y el nombre del módulo solicitados.</span><span class="sxs-lookup"><span data-stu-id="7452a-107">[in] A pointer to a [ModuleBindInfo](modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="7452a-108">enuncia Un puntero a un identificador único para `IStream` que contiene el módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="7452a-108">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="7452a-109">enuncia Un puntero a la dirección de un `IStream` objeto, que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se encuentra el módulo.</span><span class="sxs-lookup"><span data-stu-id="7452a-109">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="7452a-110">enuncia Puntero a la dirección de un `IStream` objeto, que contiene la información de depuración del programa (PDB) para el módulo solicitado, o null si no se encuentra el archivo. pdb.</span><span class="sxs-lookup"><span data-stu-id="7452a-110">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7452a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7452a-111">Return Value</span></span>  
  
|<span data-ttu-id="7452a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7452a-112">HRESULT</span></span>|<span data-ttu-id="7452a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7452a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7452a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7452a-114">S_OK</span></span>|<span data-ttu-id="7452a-115">`ProvideModule` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7452a-115">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="7452a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7452a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7452a-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7452a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7452a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7452a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7452a-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7452a-119">The call timed out.</span></span>|  
|<span data-ttu-id="7452a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7452a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7452a-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7452a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7452a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7452a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7452a-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7452a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7452a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7452a-124">E_FAIL</span></span>|<span data-ttu-id="7452a-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7452a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7452a-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7452a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7452a-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7452a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7452a-128">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="7452a-128">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="7452a-129">No se encontró el ensamblado o el recurso vinculado solicitado.</span><span class="sxs-lookup"><span data-stu-id="7452a-129">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="7452a-130">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7452a-130">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7452a-131">`pdwModuleId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="7452a-131">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7452a-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7452a-132">Remarks</span></span>  

 <span data-ttu-id="7452a-133">El valor de identidad devuelto por `pdwModuleId` se especifica mediante el host.</span><span class="sxs-lookup"><span data-stu-id="7452a-133">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="7452a-134">Los identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="7452a-134">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="7452a-135">CLR usa este valor como identificador único para la secuencia asociada.</span><span class="sxs-lookup"><span data-stu-id="7452a-135">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="7452a-136">Comprueba cada valor con los valores `pAssemblyId` devueltos por las llamadas a [ProvideAssembly](ihostassemblystore-provideassembly-method.md) y con los valores `pdwModuleId` devueltos por otras llamadas a `ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="7452a-136">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="7452a-137">Si el host devuelve el mismo valor de identificador para otro `IStream` , CLR comprueba si ya se ha asignado el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7452a-137">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="7452a-138">Si es así, CLR carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="7452a-138">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="7452a-139">Por lo tanto, el identificador tampoco debe superponerse con los identificadores de ensamblado devueltos por `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="7452a-139">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7452a-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7452a-140">Requirements</span></span>  

 <span data-ttu-id="7452a-141">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7452a-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7452a-142">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7452a-142">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7452a-143">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7452a-143">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7452a-144">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7452a-144">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7452a-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="7452a-145">See also</span></span>

- [<span data-ttu-id="7452a-146">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7452a-146">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7452a-147">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7452a-147">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="7452a-148">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7452a-148">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

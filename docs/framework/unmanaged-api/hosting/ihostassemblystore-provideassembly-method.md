---
description: 'Más información acerca de: IHostAssemblyStore::P método rovideAssembly'
title: IHostAssemblyStore::ProvideAssembly (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: f8917cb28dd3898343a7b6ee08bd54096df8cfa7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789507"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="9a731-103">IHostAssemblyStore::ProvideAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="9a731-103">IHostAssemblyStore::ProvideAssembly Method</span></span>

<span data-ttu-id="9a731-104">Obtiene una referencia a un ensamblado al que no hace referencia el [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que se devuelve desde [IHostAssemblyManager:: GetNonHostStoreAssemblies (](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="9a731-104">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="9a731-105">El Common Language Runtime (CLR) llama a `ProvideAssembly` para cada ensamblado que no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="9a731-105">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a731-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a731-106">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a731-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a731-107">Parameters</span></span>  

 `pBindInfo`  
 <span data-ttu-id="9a731-108">de Puntero a una instancia de [assemblybindinfo (](assemblybindinfo-structure.md) que el host usa para determinar ciertas características de enlace, incluida la presencia o ausencia de cualquier directiva de control de versiones y el ensamblado al que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="9a731-108">[in] A pointer to an [AssemblyBindInfo](assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="9a731-109">enuncia Un puntero a un identificador único para el ensamblado solicitado para este `IStream` .</span><span class="sxs-lookup"><span data-stu-id="9a731-109">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="9a731-110">enuncia Puntero a los datos específicos del host que se usan para determinar la evidencia del ensamblado solicitado sin necesidad de una llamada de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="9a731-110">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="9a731-111">`pHostContext` corresponde a la <xref:System.Reflection.Assembly.HostContext%2A> propiedad de la clase administrada <xref:System.Reflection.Assembly> .</span><span class="sxs-lookup"><span data-stu-id="9a731-111">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="9a731-112">enuncia Puntero a la dirección de `IStream` que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se pudo encontrar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9a731-112">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="9a731-113">enuncia Puntero a la dirección de `IStream` que contiene la información de depuración del programa (PDB) o null si no se encuentra el archivo. pdb.</span><span class="sxs-lookup"><span data-stu-id="9a731-113">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a731-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a731-114">Return Value</span></span>  
  
|<span data-ttu-id="9a731-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a731-115">HRESULT</span></span>|<span data-ttu-id="9a731-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a731-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a731-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a731-117">S_OK</span></span>|<span data-ttu-id="9a731-118">`ProvideAssembly` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a731-118">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="9a731-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a731-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a731-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a731-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a731-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a731-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a731-122">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9a731-122">The call timed out.</span></span>|  
|<span data-ttu-id="9a731-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a731-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a731-124">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9a731-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a731-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a731-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a731-126">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="9a731-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a731-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a731-127">E_FAIL</span></span>|<span data-ttu-id="9a731-128">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="9a731-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a731-129">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9a731-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a731-130">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9a731-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9a731-131">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="9a731-131">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="9a731-132">No se pudo encontrar el ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="9a731-132">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="9a731-133">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9a731-133">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9a731-134">El tamaño de búfer especificado por `pAssemblyId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="9a731-134">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a731-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9a731-135">Remarks</span></span>  

 <span data-ttu-id="9a731-136">El valor de identidad devuelto por `pAssemblyId` se especifica mediante el host.</span><span class="sxs-lookup"><span data-stu-id="9a731-136">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="9a731-137">Los identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="9a731-137">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="9a731-138">CLR usa este valor como un identificador único para la secuencia.</span><span class="sxs-lookup"><span data-stu-id="9a731-138">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="9a731-139">Comprueba cada valor con los valores `pAssemblyId` devueltos por otras llamadas a `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="9a731-139">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="9a731-140">Si el host devuelve el mismo `pAssemblyId` valor para otro `IStream` , CLR comprueba si ya se ha asignado el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="9a731-140">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="9a731-141">En ese caso, el tiempo de ejecución carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="9a731-141">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a731-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a731-142">Requirements</span></span>  

 <span data-ttu-id="9a731-143">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a731-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a731-144">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9a731-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a731-145">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a731-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a731-146">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a731-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a731-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a731-147">See also</span></span>

- [<span data-ttu-id="9a731-148">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a731-148">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9a731-149">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a731-149">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="9a731-150">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a731-150">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

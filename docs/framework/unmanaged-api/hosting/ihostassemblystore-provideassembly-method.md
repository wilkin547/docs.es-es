---
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
ms.openlocfilehash: db65519579104dd01816bb6d7cacaec947f24f53
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680874"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="6a37a-102">IHostAssemblyStore::ProvideAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="6a37a-102">IHostAssemblyStore::ProvideAssembly Method</span></span>

<span data-ttu-id="6a37a-103">Obtiene una referencia a un ensamblado al que no hace referencia el [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que se devuelve desde [IHostAssemblyManager:: GetNonHostStoreAssemblies (](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="6a37a-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="6a37a-104">El Common Language Runtime (CLR) llama a `ProvideAssembly` para cada ensamblado que no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="6a37a-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a37a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a37a-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a37a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a37a-106">Parameters</span></span>  

 `pBindInfo`  
 <span data-ttu-id="6a37a-107">de Puntero a una instancia de [assemblybindinfo (](assemblybindinfo-structure.md) que el host usa para determinar ciertas características de enlace, incluida la presencia o ausencia de cualquier directiva de control de versiones y el ensamblado al que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="6a37a-107">[in] A pointer to an [AssemblyBindInfo](assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="6a37a-108">enuncia Un puntero a un identificador único para el ensamblado solicitado para este `IStream` .</span><span class="sxs-lookup"><span data-stu-id="6a37a-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="6a37a-109">enuncia Puntero a los datos específicos del host que se usan para determinar la evidencia del ensamblado solicitado sin necesidad de una llamada de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="6a37a-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="6a37a-110">`pHostContext` corresponde a la <xref:System.Reflection.Assembly.HostContext%2A> propiedad de la clase administrada <xref:System.Reflection.Assembly> .</span><span class="sxs-lookup"><span data-stu-id="6a37a-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="6a37a-111">enuncia Puntero a la dirección de `IStream` que contiene la imagen ejecutable portable (PE) que se va a cargar, o null si no se pudo encontrar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6a37a-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="6a37a-112">enuncia Puntero a la dirección de `IStream` que contiene la información de depuración del programa (PDB) o null si no se encuentra el archivo. pdb.</span><span class="sxs-lookup"><span data-stu-id="6a37a-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a37a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a37a-113">Return Value</span></span>  
  
|<span data-ttu-id="6a37a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a37a-114">HRESULT</span></span>|<span data-ttu-id="6a37a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a37a-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a37a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a37a-116">S_OK</span></span>|<span data-ttu-id="6a37a-117">`ProvideAssembly` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a37a-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="6a37a-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6a37a-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6a37a-119">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a37a-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6a37a-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6a37a-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6a37a-121">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6a37a-121">The call timed out.</span></span>|  
|<span data-ttu-id="6a37a-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6a37a-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6a37a-123">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6a37a-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6a37a-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6a37a-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6a37a-125">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6a37a-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6a37a-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6a37a-126">E_FAIL</span></span>|<span data-ttu-id="6a37a-127">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6a37a-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6a37a-128">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6a37a-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6a37a-129">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6a37a-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6a37a-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="6a37a-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="6a37a-131">No se pudo encontrar el ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="6a37a-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="6a37a-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="6a37a-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="6a37a-133">El tamaño de búfer especificado por `pAssemblyId` no es lo suficientemente grande como para contener el identificador que el host desea devolver.</span><span class="sxs-lookup"><span data-stu-id="6a37a-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a37a-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a37a-134">Remarks</span></span>  

 <span data-ttu-id="6a37a-135">El valor de identidad devuelto por `pAssemblyId` se especifica mediante el host.</span><span class="sxs-lookup"><span data-stu-id="6a37a-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="6a37a-136">Los identificadores deben ser únicos dentro de la duración de un proceso.</span><span class="sxs-lookup"><span data-stu-id="6a37a-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="6a37a-137">CLR usa este valor como un identificador único para la secuencia.</span><span class="sxs-lookup"><span data-stu-id="6a37a-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="6a37a-138">Comprueba cada valor con los valores `pAssemblyId` devueltos por otras llamadas a `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="6a37a-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="6a37a-139">Si el host devuelve el mismo `pAssemblyId` valor para otro `IStream` , CLR comprueba si ya se ha asignado el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="6a37a-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="6a37a-140">En ese caso, el tiempo de ejecución carga la copia existente de la imagen en lugar de asignar una nueva.</span><span class="sxs-lookup"><span data-stu-id="6a37a-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a37a-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a37a-141">Requirements</span></span>  

 <span data-ttu-id="6a37a-142">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a37a-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a37a-143">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6a37a-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a37a-144">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a37a-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a37a-145">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a37a-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a37a-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a37a-146">See also</span></span>

- [<span data-ttu-id="6a37a-147">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a37a-147">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="6a37a-148">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a37a-148">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="6a37a-149">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a37a-149">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

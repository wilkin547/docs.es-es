---
title: IHostAssemblyManager::GetNonHostStoreAssemblies (Método)
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
ms.openlocfilehash: a34b907514376927d8a1aa66b136916108b704d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681150"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="b699e-102">IHostAssemblyManager::GetNonHostStoreAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="b699e-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>

<span data-ttu-id="b699e-103">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que cargue el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b699e-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b699e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b699e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b699e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b699e-105">Parameters</span></span>  

 `ppReferenceList`  
 <span data-ttu-id="b699e-106">enuncia Puntero a la dirección de un `ICLRAssemblyReferenceList` que contiene una lista de referencias a los ensamblados que el host espera que el CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="b699e-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b699e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b699e-107">Return Value</span></span>  
  
|<span data-ttu-id="b699e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b699e-108">HRESULT</span></span>|<span data-ttu-id="b699e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b699e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b699e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b699e-110">S_OK</span></span>|<span data-ttu-id="b699e-111">`GetNonHostStoreAssemblies` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b699e-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="b699e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b699e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b699e-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b699e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b699e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b699e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b699e-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b699e-115">The call timed out.</span></span>|  
|<span data-ttu-id="b699e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b699e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b699e-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b699e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b699e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b699e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b699e-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="b699e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b699e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b699e-120">E_FAIL</span></span>|<span data-ttu-id="b699e-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b699e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b699e-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b699e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b699e-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b699e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b699e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b699e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b699e-125">No había suficiente memoria disponible para crear la lista de referencias para el solicitado `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="b699e-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b699e-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b699e-126">Remarks</span></span>  

 <span data-ttu-id="b699e-127">CLR resuelve las referencias utilizando el siguiente conjunto de instrucciones:</span><span class="sxs-lookup"><span data-stu-id="b699e-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="b699e-128">En primer lugar, consulta la lista de referencias de ensamblado devueltas por `GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="b699e-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="b699e-129">Si el ensamblado aparece en la lista, CLR se enlaza a él normalmente.</span><span class="sxs-lookup"><span data-stu-id="b699e-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="b699e-130">Si el ensamblado no aparece en la lista y el host ha proporcionado una implementación de [IHostAssemblyStore](ihostassemblystore-interface.md), CLR llama a [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) para permitir que el host proporcione el ensamblado con el que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="b699e-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="b699e-131">De lo contrario, CLR no puede enlazar con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b699e-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="b699e-132">Si el host establece `ppReferenceList` en null, CLR sondea primero la caché global de ensamblados, llama a `ProvideAssembly` y, a continuación, sondea la base de la aplicación para resolver una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b699e-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b699e-133">Tras la inicialización, CLR llama `GetNonHostStoreAssemblies` solo una vez.</span><span class="sxs-lookup"><span data-stu-id="b699e-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="b699e-134">No se llama de nuevo al método.</span><span class="sxs-lookup"><span data-stu-id="b699e-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b699e-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b699e-135">Requirements</span></span>  

 <span data-ttu-id="b699e-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b699e-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b699e-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b699e-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b699e-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b699e-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b699e-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b699e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b699e-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b699e-140">See also</span></span>

- [<span data-ttu-id="b699e-141">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b699e-141">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b699e-142">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b699e-142">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="b699e-143">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b699e-143">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

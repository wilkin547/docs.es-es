---
description: 'Más información acerca de: IHostAssemblyManager:: GetNonHostStoreAssemblies ((método)'
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
ms.openlocfilehash: ef551db45428b2381dfeae8f722257241a4deaf0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709053"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="01037-103">IHostAssemblyManager::GetNonHostStoreAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="01037-103">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>

<span data-ttu-id="01037-104">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que cargue el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="01037-104">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01037-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01037-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01037-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01037-106">Parameters</span></span>  

 `ppReferenceList`  
 <span data-ttu-id="01037-107">enuncia Puntero a la dirección de un `ICLRAssemblyReferenceList` que contiene una lista de referencias a los ensamblados que el host espera que el CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="01037-107">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01037-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="01037-108">Return Value</span></span>  
  
|<span data-ttu-id="01037-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01037-109">HRESULT</span></span>|<span data-ttu-id="01037-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="01037-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01037-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="01037-111">S_OK</span></span>|<span data-ttu-id="01037-112">`GetNonHostStoreAssemblies` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="01037-112">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="01037-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01037-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01037-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="01037-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01037-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01037-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01037-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="01037-116">The call timed out.</span></span>|  
|<span data-ttu-id="01037-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01037-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01037-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="01037-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01037-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01037-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01037-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="01037-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01037-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01037-121">E_FAIL</span></span>|<span data-ttu-id="01037-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="01037-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01037-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="01037-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01037-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="01037-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="01037-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="01037-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="01037-126">No había suficiente memoria disponible para crear la lista de referencias para el solicitado `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="01037-126">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01037-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="01037-127">Remarks</span></span>  

 <span data-ttu-id="01037-128">CLR resuelve las referencias utilizando el siguiente conjunto de instrucciones:</span><span class="sxs-lookup"><span data-stu-id="01037-128">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="01037-129">En primer lugar, consulta la lista de referencias de ensamblado devueltas por `GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="01037-129">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="01037-130">Si el ensamblado aparece en la lista, CLR se enlaza a él normalmente.</span><span class="sxs-lookup"><span data-stu-id="01037-130">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="01037-131">Si el ensamblado no aparece en la lista y el host ha proporcionado una implementación de [IHostAssemblyStore](ihostassemblystore-interface.md), CLR llama a [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) para permitir que el host proporcione el ensamblado con el que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="01037-131">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="01037-132">De lo contrario, CLR no puede enlazar con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="01037-132">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="01037-133">Si el host establece `ppReferenceList` en null, CLR sondea primero la caché global de ensamblados, llama a `ProvideAssembly` y, a continuación, sondea la base de la aplicación para resolver una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="01037-133">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01037-134">Tras la inicialización, CLR llama `GetNonHostStoreAssemblies` solo una vez.</span><span class="sxs-lookup"><span data-stu-id="01037-134">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="01037-135">No se llama de nuevo al método.</span><span class="sxs-lookup"><span data-stu-id="01037-135">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01037-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01037-136">Requirements</span></span>  

 <span data-ttu-id="01037-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01037-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01037-138">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="01037-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01037-139">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01037-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01037-140">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01037-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01037-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="01037-141">See also</span></span>

- [<span data-ttu-id="01037-142">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="01037-142">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="01037-143">IHostAssemblyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="01037-143">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="01037-144">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="01037-144">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)

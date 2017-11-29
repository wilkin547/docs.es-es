---
title: "ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cf0bccebbfe5620ef329cc8c6f72582a7afe85a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="359e4-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)</span><span class="sxs-lookup"><span data-stu-id="359e4-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>
<span data-ttu-id="359e4-103">[Compatible con .NET Framework 4.6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="359e4-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="359e4-104">Devuelve un enumerador para todos los métodos que se definen en un determinado módulo de NGen y en línea un método determinado.</span><span class="sxs-lookup"><span data-stu-id="359e4-104">Returns an enumerator to all the methods that          are defined in  a given NGen module and          inline a given method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359e4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="359e4-105">Syntax</span></span>  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="359e4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="359e4-106">Parameters</span></span>  
 `inlinersModuleId`  
 <span data-ttu-id="359e4-107">[in] El identificador de un módulo NGen.</span><span class="sxs-lookup"><span data-stu-id="359e4-107">[in] The identifier of an NGen module.</span></span>  
  
 `inlineeModuleId`  
 <span data-ttu-id="359e4-108">[in] El identificador de un módulo que define `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="359e4-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="359e4-109">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="359e4-109">See the Remarks section for more information.</span></span>  
  
 `inlineeMethodId`  
 <span data-ttu-id="359e4-110">[in] El identificador de un método entre línea.</span><span class="sxs-lookup"><span data-stu-id="359e4-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="359e4-111">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="359e4-111">See the Remarks section for more information.</span></span>  
  
 `incompleteData`  
 <span data-ttu-id="359e4-112">[out] Una marca que indica si `ppEnum` contiene todos los métodos de inserción de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="359e4-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="359e4-113">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="359e4-113">See the Remarks section for more information.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="359e4-114">[out] Un puntero a la dirección de un enumerador</span><span class="sxs-lookup"><span data-stu-id="359e4-114">[out] A pointer to the address of an enumerator</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="359e4-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="359e4-115">Remarks</span></span>  
 <span data-ttu-id="359e4-116">`inlineeModuleId`y `inlineeMethodId` juntos forman el identificador completo para el método que podría estar entre línea.</span><span class="sxs-lookup"><span data-stu-id="359e4-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="359e4-117">Por ejemplo, suponga módulo `A` define un método `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="359e4-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 <span data-ttu-id="359e4-118">módulo Bdefines y `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="359e4-118">and module Bdefines `Fancy.AddTwice`:</span></span>  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 <span data-ttu-id="359e4-119">Supongamos también que `Fancy.AddTwice` elementos incorporados en la llamada a `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="359e4-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="359e4-120">Un generador de perfiles podría utilizar este enumerador para buscar todos los métodos definen en el módulo B qué alineado `Simple.Add`, y el resultado podría enumerar `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="359e4-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="359e4-121">`inlineeModuleId`es el identificador del módulo `A`, y `inlineeeMethodId` es el identificador de `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="359e4-121">`inlineeModuleId` is the identifier of module `A`,   and `inlineeeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>  
  
 <span data-ttu-id="359e4-122">Si `incompleteData` es true después de la función devuelve el enumerador no contiene todos los métodos de inserción un método determinado.</span><span class="sxs-lookup"><span data-stu-id="359e4-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="359e4-123">Esto puede suceder cuando uno o más dependencias directas o indirectas del módulo inliners aún no se han cargado todavía.</span><span class="sxs-lookup"><span data-stu-id="359e4-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="359e4-124">Si un generador de perfiles necesita datos precisos, debe reintentar más tarde cuando se cargan varios módulos, preferiblemente en cada carga de módulo.</span><span class="sxs-lookup"><span data-stu-id="359e4-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>  
  
 <span data-ttu-id="359e4-125">El `EnumNgenModuleMethodsInliningThisMethod` método se puede utilizar para evitar limitaciones en la inclusión de ReJIT.</span><span class="sxs-lookup"><span data-stu-id="359e4-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="359e4-126">ReJIT permite un generador de perfiles cambie la implementación de un método y, a continuación, crear código nuevo para el mismo sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="359e4-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="359e4-127">Por ejemplo, podríamos cambiar `Simple.Add` como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="359e4-127">For example, we could change `Simple.Add` as follows:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 <span data-ttu-id="359e4-128">Sin embargo porque `Fancy.AddTwice` tiene ya insertadas `Simple.Add`, sigue teniendo el mismo comportamiento que antes.</span><span class="sxs-lookup"><span data-stu-id="359e4-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="359e4-129">Para evitar esa limitación, el llamador tiene que buscar todos los métodos en todos los módulos que en línea `Simple.Add` y usar `ICorProfilerInfo5::RequestRejit` en cada uno de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="359e4-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="359e4-130">Cuando los métodos se volverán a compilar, tendrán el nuevo comportamiento de `Simple.Add` en lugar del comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="359e4-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="359e4-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="359e4-131">Requirements</span></span>  
 <span data-ttu-id="359e4-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="359e4-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="359e4-133">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="359e4-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="359e4-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="359e4-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="359e4-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="359e4-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="359e4-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="359e4-136">See Also</span></span>  
 [<span data-ttu-id="359e4-137">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="359e4-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)

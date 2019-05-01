---
title: Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67ae413ae8944757fc90bcde752b9a5fe53cc68f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948530"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="98dd8-102">Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="98dd8-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="98dd8-103">Devuelve un enumerador para todos los métodos que se definen en un determinado módulo NGen y en línea un método determinado.</span><span class="sxs-lookup"><span data-stu-id="98dd8-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="98dd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98dd8-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="98dd8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98dd8-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="98dd8-106">[in] El identificador de un módulo NGen.</span><span class="sxs-lookup"><span data-stu-id="98dd8-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="98dd8-107">[in] El identificador de un módulo que define `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="98dd8-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="98dd8-108">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="98dd8-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="98dd8-109">[in] El identificador de un método entre líneas.</span><span class="sxs-lookup"><span data-stu-id="98dd8-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="98dd8-110">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="98dd8-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="98dd8-111">[out] Una marca que indica si `ppEnum` contiene todos los métodos de inserción de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="98dd8-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="98dd8-112">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="98dd8-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="98dd8-113">[out] Un puntero a la dirección de un enumerador</span><span class="sxs-lookup"><span data-stu-id="98dd8-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="98dd8-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98dd8-114">Remarks</span></span>

<span data-ttu-id="98dd8-115">`inlineeModuleId` y `inlineeMethodId` juntos forman el identificador completo para el método que podría insertarse.</span><span class="sxs-lookup"><span data-stu-id="98dd8-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="98dd8-116">Por ejemplo, suponga módulo `A` define un método `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="98dd8-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="98dd8-117">y define el módulo B `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="98dd8-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="98dd8-118">Supongamos también que `Fancy.AddTwice` elementos incorporados en la llamada a `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="98dd8-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="98dd8-119">Un generador de perfiles podría utilizar este enumerador para buscar todos los métodos definen en el módulo B en qué línea `Simple.Add`, y el resultado podría enumerar `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="98dd8-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="98dd8-120">`inlineeModuleId` es el identificador del módulo `A`, y `inlineeMethodId` es el identificador de `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="98dd8-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="98dd8-121">Si `incompleteData` es true después de la función que devuelve el enumerador no contiene todos los métodos de inserción un método determinado.</span><span class="sxs-lookup"><span data-stu-id="98dd8-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="98dd8-122">Esto puede suceder cuando uno o más dependencias directas o indirectas de módulo inliners aún no se ha cargado aún.</span><span class="sxs-lookup"><span data-stu-id="98dd8-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="98dd8-123">Si un generador de perfiles necesita datos precisos, debe a intentarlo más tarde cuando se cargan más módulos, preferiblemente en cada carga de módulo.</span><span class="sxs-lookup"><span data-stu-id="98dd8-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="98dd8-124">El `EnumNgenModuleMethodsInliningThisMethod` método puede utilizarse para solucionar las limitaciones de inclusión entre líneas para ReJIT.</span><span class="sxs-lookup"><span data-stu-id="98dd8-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="98dd8-125">ReJIT permite a un generador de perfiles cambie la implementación de un método y, a continuación, crear código nuevo para ella sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="98dd8-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="98dd8-126">Por ejemplo, podríamos cambiar `Simple.Add` como sigue:</span><span class="sxs-lookup"><span data-stu-id="98dd8-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="98dd8-127">Sin embargo porque `Fancy.AddTwice` tiene ya insertadas `Simple.Add`, sigue teniendo el mismo comportamiento como antes.</span><span class="sxs-lookup"><span data-stu-id="98dd8-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="98dd8-128">Para solucionar esta limitación, el llamador tiene que buscar todos los métodos en todos los módulos directamente `Simple.Add` y usar `ICorProfilerInfo5::RequestRejit` en cada uno de esos métodos.</span><span class="sxs-lookup"><span data-stu-id="98dd8-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="98dd8-129">Cuando los métodos se volverán a compilar, tendrá el nuevo comportamiento de `Simple.Add` en lugar del comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="98dd8-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="98dd8-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98dd8-130">Requirements</span></span>

<span data-ttu-id="98dd8-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98dd8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="98dd8-132">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98dd8-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="98dd8-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98dd8-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="98dd8-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98dd8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="98dd8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="98dd8-135">See also</span></span>

- [<span data-ttu-id="98dd8-136">ICorProfilerInfo6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98dd8-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
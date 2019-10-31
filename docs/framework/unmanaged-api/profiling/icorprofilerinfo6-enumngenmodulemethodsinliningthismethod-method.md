---
title: Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130384"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="9244c-102">Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="9244c-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="9244c-103">Devuelve un enumerador a todos los métodos que se definen en un módulo NGen determinado e inserta un método determinado.</span><span class="sxs-lookup"><span data-stu-id="9244c-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="9244c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9244c-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="9244c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9244c-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="9244c-106">de Identificador de un módulo NGen.</span><span class="sxs-lookup"><span data-stu-id="9244c-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="9244c-107">de Identificador de un módulo que define `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="9244c-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="9244c-108">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9244c-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="9244c-109">de Identificador de un método insertado.</span><span class="sxs-lookup"><span data-stu-id="9244c-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="9244c-110">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9244c-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="9244c-111">enuncia Marca que indica si `ppEnum` contiene todos los métodos que inlinean un método determinado.</span><span class="sxs-lookup"><span data-stu-id="9244c-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="9244c-112">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9244c-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="9244c-113">enuncia Puntero a la dirección de un enumerador.</span><span class="sxs-lookup"><span data-stu-id="9244c-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="9244c-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9244c-114">Remarks</span></span>

<span data-ttu-id="9244c-115">`inlineeModuleId` y `inlineeMethodId` forman conjuntamente el identificador completo para el método que podría estar insertado.</span><span class="sxs-lookup"><span data-stu-id="9244c-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="9244c-116">Por ejemplo, suponga que el módulo `A` define un método `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="9244c-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="9244c-117">y el módulo B define `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="9244c-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="9244c-118">También se supone que `Fancy.AddTwice` inserta la llamada a `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="9244c-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="9244c-119">Un generador de perfiles podría usar este enumerador para buscar todos los métodos definidos en el módulo B que `Simple.Add`insertados y el resultado Enumeraría `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="9244c-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="9244c-120">`inlineeModuleId` es el identificador de `A`del módulo y `inlineeMethodId` es el identificador de `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="9244c-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="9244c-121">Si `incompleteData` es true después de que la función devuelva un valor, el enumerador no contiene todos los métodos que inlinean un método determinado.</span><span class="sxs-lookup"><span data-stu-id="9244c-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="9244c-122">Esto puede ocurrir cuando todavía no se han cargado una o más dependencias directas o indirectas del módulo inlineers.</span><span class="sxs-lookup"><span data-stu-id="9244c-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="9244c-123">Si un generador de perfiles necesita datos precisos, debe volver a intentarlo más tarde cuando se carguen más módulos, preferiblemente en cada carga de módulo.</span><span class="sxs-lookup"><span data-stu-id="9244c-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="9244c-124">El método `EnumNgenModuleMethodsInliningThisMethod` se puede usar para solucionar las limitaciones de la inserción de ReJIT.</span><span class="sxs-lookup"><span data-stu-id="9244c-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="9244c-125">ReJIT permite que un generador de perfiles cambie la implementación de un método y, a continuación, cree código nuevo sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="9244c-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="9244c-126">Por ejemplo, podríamos cambiar `Simple.Add` como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="9244c-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="9244c-127">Sin embargo, dado que `Fancy.AddTwice` ya se ha insertado `Simple.Add`, sigue teniendo el mismo comportamiento que antes.</span><span class="sxs-lookup"><span data-stu-id="9244c-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="9244c-128">Para solucionar esta limitación, el autor de la llamada tiene que buscar todos los métodos en todos los módulos que insertan `Simple.Add` y utilizar `ICorProfilerInfo5::RequestRejit` en cada uno de esos métodos.</span><span class="sxs-lookup"><span data-stu-id="9244c-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="9244c-129">Cuando se vuelven a compilar los métodos, tendrán el nuevo comportamiento de `Simple.Add` en lugar del comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="9244c-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="9244c-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9244c-130">Requirements</span></span>

<span data-ttu-id="9244c-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9244c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9244c-132">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9244c-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="9244c-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9244c-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9244c-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9244c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9244c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="9244c-135">See also</span></span>

- [<span data-ttu-id="9244c-136">ICorProfilerInfo6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9244c-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)

---
description: 'Más información sobre: ICorProfilerInfo6:: EnumNgenModuleMethodsInliningThisMethod (método)'
title: Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: bd43dcecabe9a75f7ce3a94996727b192574e321
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737173"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="0779e-103">Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="0779e-103">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="0779e-104">Devuelve un enumerador a todos los métodos que se definen en un módulo NGen determinado e inserta un método determinado.</span><span class="sxs-lookup"><span data-stu-id="0779e-104">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="0779e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0779e-105">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="0779e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0779e-106">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="0779e-107">de Identificador de un módulo NGen.</span><span class="sxs-lookup"><span data-stu-id="0779e-107">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="0779e-108">de Identificador de un módulo que define `inlineeMethodId` .</span><span class="sxs-lookup"><span data-stu-id="0779e-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="0779e-109">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0779e-109">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="0779e-110">de Identificador de un método insertado.</span><span class="sxs-lookup"><span data-stu-id="0779e-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="0779e-111">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0779e-111">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="0779e-112">enuncia Marca que indica si `ppEnum` contiene todos los métodos que inlinean un método determinado.</span><span class="sxs-lookup"><span data-stu-id="0779e-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="0779e-113">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0779e-113">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="0779e-114">enuncia Puntero a la dirección de un enumerador.</span><span class="sxs-lookup"><span data-stu-id="0779e-114">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="0779e-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0779e-115">Remarks</span></span>

<span data-ttu-id="0779e-116">`inlineeModuleId` y `inlineeMethodId` forman conjuntamente el identificador completo para el método que podría estar insertado.</span><span class="sxs-lookup"><span data-stu-id="0779e-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="0779e-117">Por ejemplo, Imagine que `A` el módulo define un método `Simple.Add` :</span><span class="sxs-lookup"><span data-stu-id="0779e-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="0779e-118">y el módulo B define `Fancy.AddTwice` :</span><span class="sxs-lookup"><span data-stu-id="0779e-118">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="0779e-119">También se supone que `Fancy.AddTwice` inserta la llamada a `SimpleAdd` .</span><span class="sxs-lookup"><span data-stu-id="0779e-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="0779e-120">Un generador de perfiles podría usar este enumerador para buscar todos los métodos definidos en el módulo B que están alineados `Simple.Add` y el resultado Enumeraría `AddTwice` .</span><span class="sxs-lookup"><span data-stu-id="0779e-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="0779e-121">`inlineeModuleId` es el identificador del módulo `A` y `inlineeMethodId` es el identificador de `Simple.Add(int a, int b)` .</span><span class="sxs-lookup"><span data-stu-id="0779e-121">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="0779e-122">Si `incompleteData` es true después de que la función devuelva un valor, el enumerador no contiene todos los métodos que inlinean un método determinado.</span><span class="sxs-lookup"><span data-stu-id="0779e-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="0779e-123">Esto puede ocurrir cuando todavía no se han cargado una o más dependencias directas o indirectas del módulo inlineers.</span><span class="sxs-lookup"><span data-stu-id="0779e-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="0779e-124">Si un generador de perfiles necesita datos precisos, debe volver a intentarlo más tarde cuando se carguen más módulos, preferiblemente en cada carga de módulo.</span><span class="sxs-lookup"><span data-stu-id="0779e-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="0779e-125">El `EnumNgenModuleMethodsInliningThisMethod` método se puede usar para solucionar las limitaciones de la inserción de ReJIT.</span><span class="sxs-lookup"><span data-stu-id="0779e-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="0779e-126">ReJIT permite que un generador de perfiles cambie la implementación de un método y, a continuación, cree código nuevo sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="0779e-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="0779e-127">Por ejemplo, podríamos cambiar de la `Simple.Add` siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0779e-127">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="0779e-128">Sin embargo `Fancy.AddTwice` , dado que ya se ha insertado `Simple.Add` , sigue teniendo el mismo comportamiento que antes.</span><span class="sxs-lookup"><span data-stu-id="0779e-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="0779e-129">Para solucionar esta limitación, el llamador tiene que buscar todos los métodos en todos los módulos que se alinean `Simple.Add` y usan `ICorProfilerInfo5::RequestRejit` en cada uno de esos métodos.</span><span class="sxs-lookup"><span data-stu-id="0779e-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="0779e-130">Cuando se vuelven a compilar los métodos, tendrán el nuevo comportamiento de `Simple.Add` en lugar del comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="0779e-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="0779e-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0779e-131">Requirements</span></span>

<span data-ttu-id="0779e-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0779e-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0779e-133">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0779e-133">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="0779e-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0779e-134">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0779e-135">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0779e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0779e-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0779e-136">See also</span></span>

- [<span data-ttu-id="0779e-137">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="0779e-137">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)

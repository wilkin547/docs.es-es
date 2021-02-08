---
description: 'Más información sobre: ICorProfilerCallback5:: Conditionalweaktableelementreferences ((método)'
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ConditionalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
ms.openlocfilehash: 40114f6e1d80719eceaf2dbc398b74c1e790c76a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788675"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a><span data-ttu-id="258d0-103">ICorProfilerCallback5::ConditionalWeakTableElementReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="258d0-103">ICorProfilerCallback5::ConditionalWeakTableElementReferences Method</span></span>

<span data-ttu-id="258d0-104">Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="258d0-104">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>

## <a name="syntax"></a><span data-ttu-id="258d0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="258d0-105">Syntax</span></span>

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a><span data-ttu-id="258d0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="258d0-106">Parameters</span></span>

`cRootRefs`\
<span data-ttu-id="258d0-107">[in] Número de elementos en las matrices `keyRefIds`, `valueRefIds` y `rootIds`.</span><span class="sxs-lookup"><span data-stu-id="258d0-107">[in] The number of elements in the `keyRefIds`, `valueRefIds`, and `rootIds` arrays.</span></span>

`keyRefIds`\
<span data-ttu-id="258d0-108">[in] Matriz de identificadores de objeto, cada uno de los cuales contiene el `ObjectID` del elemento principal en el par de controladores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="258d0-108">[in] An array of object IDs, each of which contains the `ObjectID` for the primary element in the dependent handle pair.</span></span>

`valueRefIds`\
<span data-ttu-id="258d0-109">[in] Matriz de identificadores de objeto, cada uno de los cuales contiene el `ObjectID` del elemento secundario en el par de controladores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="258d0-109">[in] An array of object IDs, each of which contains the `ObjectID` for the secondary element in the dependent handle pair.</span></span> <span data-ttu-id="258d0-110">( `keyRefIds[i]` mantiene `valueRefIds[i]` activo).</span><span class="sxs-lookup"><span data-stu-id="258d0-110">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span></span>

`rootIds`\
<span data-ttu-id="258d0-111">[in] Matriz de valores `GCHandleID` que apuntan a un entero que contiene información adicional sobre la raíz de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="258d0-111">[in] An array of `GCHandleID` values that point to an integer that contains additional information about the garbage collection root.</span></span>

<span data-ttu-id="258d0-112">Ninguno de los valores `ObjectID` devueltos por el método `ConditionalWeakTableElementReferences` son válidos durante la devolución de llamada en sí, porque el recolector de elementos no utilizados puede estar en proceso de mover objetos de ubicaciones anteriores a nuevas.</span><span class="sxs-lookup"><span data-stu-id="258d0-112">None of the `ObjectID` values returned by the `ConditionalWeakTableElementReferences` method are valid during the callback itself, because the garbage collector may be in the process of moving objects from old to new locations.</span></span> <span data-ttu-id="258d0-113">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `ConditionalWeakTableElementReferences`.</span><span class="sxs-lookup"><span data-stu-id="258d0-113">Therefore, profilers should not attempt to inspect objects during a `ConditionalWeakTableElementReferences` call.</span></span> <span data-ttu-id="258d0-114">En `GarbageCollectionFinished`, todos los objetos se han movido a sus nuevas ubicaciones y puede que la inspección se haya realizado.</span><span class="sxs-lookup"><span data-stu-id="258d0-114">At `GarbageCollectionFinished`, all objects have been moved to their new locations, and inspection may be done.</span></span>

## <a name="example"></a><span data-ttu-id="258d0-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="258d0-115">Example</span></span>

<span data-ttu-id="258d0-116">En el ejemplo de código siguiente se muestra cómo implementar [ICorProfilerCallback5](icorprofilercallback5-interface.md) y usar este método.</span><span class="sxs-lookup"><span data-stu-id="258d0-116">The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.</span></span>

```cpp
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(
    ULONG      cRootRefs,
    ObjectID   keyRefIds[],
    ObjectID   valueRefIds[],
    GCHandleID rootIds[])
{
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");
    for (unsigned int i = 0; i < cRootRefs; ++i)
    {
        // Save dependency to XML for later retrieval
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or store dependency to an internal map
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or add arc to object graph
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);
    }
    return S_OK;
}
```

## <a name="remarks"></a><span data-ttu-id="258d0-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="258d0-117">Remarks</span></span>

<span data-ttu-id="258d0-118">Un generador de perfiles para el .NET Framework 4,5 o versiones posteriores implementa la interfaz [ICorProfilerCallback5](icorprofilercallback5-interface.md) y registra las dependencias especificadas por el `ConditionalWeakTableElementReferences` método.</span><span class="sxs-lookup"><span data-stu-id="258d0-118">A profiler for the .NET Framework 4.5 or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span></span> <span data-ttu-id="258d0-119">`ICorProfilerCallback5` proporciona el conjunto completo de dependencias entre los objetos activos que representan `ConditionalWeakTable` las entradas.</span><span class="sxs-lookup"><span data-stu-id="258d0-119">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span></span> <span data-ttu-id="258d0-120">Estas dependencias y las referencias de campo de miembro especificadas por el método [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) permiten a un generador de perfiles administrado generar el gráfico de objeto completo de objetos activos.</span><span class="sxs-lookup"><span data-stu-id="258d0-120">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span></span>

## <a name="requirements"></a><span data-ttu-id="258d0-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="258d0-121">Requirements</span></span>

<span data-ttu-id="258d0-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="258d0-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="258d0-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="258d0-123">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="258d0-124">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="258d0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="258d0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="258d0-125">See also</span></span>

- [<span data-ttu-id="258d0-126">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="258d0-126">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)

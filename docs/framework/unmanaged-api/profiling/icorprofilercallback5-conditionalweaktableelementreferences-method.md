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
ms.openlocfilehash: ded43da029fe0b4c2a645823e62ca66b480f095c
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760280"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a>ICorProfilerCallback5::ConditionalWeakTableElementReferences (Método)

Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a>Parámetros

`cRootRefs` de El número de elementos de las `keyRefIds` `valueRefIds` matrices, y `rootIds` .

`keyRefIds` de Matriz de identificadores de objeto, cada uno de los cuales contiene el objeto del `ObjectID` elemento principal en el par de identificadores dependientes.

`valueRefIds` de Matriz de identificadores de objeto, cada uno de los cuales contiene el objeto del `ObjectID` elemento secundario en el par de identificadores dependientes. ( `keyRefIds[i]` mantiene `valueRefIds[i]` activo).

`rootIds` de Matriz de `GCHandleID` valores que apuntan a un entero que contiene información adicional sobre la raíz de la recolección de elementos no utilizados.

Ninguno de los valores `ObjectID` devueltos por el método `ConditionalWeakTableElementReferences` son válidos durante la devolución de llamada en sí, porque el recolector de elementos no utilizados puede estar en proceso de mover objetos de ubicaciones anteriores a nuevas. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `ConditionalWeakTableElementReferences`. En `GarbageCollectionFinished`, todos los objetos se han movido a sus nuevas ubicaciones y puede que la inspección se haya realizado.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra cómo implementar [ICorProfilerCallback5](icorprofilercallback5-interface.md) y usar este método.

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

## <a name="remarks"></a>Observaciones

Un generador de perfiles para el .NET Framework 4,5 o versiones posteriores implementa la interfaz [ICorProfilerCallback5](icorprofilercallback5-interface.md) y registra las dependencias especificadas por el `ConditionalWeakTableElementReferences` método. `ICorProfilerCallback5` proporciona el conjunto completo de dependencias entre los objetos activos que representan `ConditionalWeakTable` las entradas. Estas dependencias y las referencias de campo de miembro especificadas por el método [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) permiten a un generador de perfiles administrado generar el gráfico de objeto completo de objetos activos.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorProf.idl, CorProf.h

**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback5 (interfaz)](icorprofilercallback5-interface.md)

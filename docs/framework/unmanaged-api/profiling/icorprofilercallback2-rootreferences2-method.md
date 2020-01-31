---
title: ICorProfilerCallback2::RootReferences2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: a9ce9a7a56847efcadf09924ffc56c41f20a1c58
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865732"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>ICorProfilerCallback2::RootReferences2 (Método)
Notifica al generador de perfiles las referencias raíz después de que se haya producido la recolección de elementos no utilizados. Este método es una extensión del método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Parameters  
 `cRootRefs`  
 de El número de elementos de las matrices `rootRefIds`, `rootKinds`, `rootFlags`y `rootIds`.  
  
 `rootRefIds`  
 de Matriz de identificadores de objeto, cada uno de los cuales hace referencia a un objeto estático o a un objeto de la pila. Los elementos de la matriz de `rootKinds` proporcionan información para clasificar los elementos correspondientes de la matriz de `rootRefIds`.  
  
 `rootKinds`  
 de Matriz de valores de [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) que indican el tipo de la raíz de la recolección de elementos no utilizados.  
  
 `rootFlags`  
 de Matriz de valores de [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) que describen las propiedades de una raíz de recolección de elementos no utilizados.  
  
 `rootIds`  
 de Matriz de valores de UINT_PTR que apuntan a un entero que contiene información adicional sobre la raíz de la recolección de elementos no utilizados, dependiendo del valor del parámetro `rootKinds`.  
  
 Si el tipo de la raíz es una pila, el identificador raíz es para la función que contiene la variable. Si el identificador raíz es 0, la función es una función sin nombre que es interna de CLR. Si el tipo de la raíz es un identificador, el identificador raíz es para el identificador de recolección de elementos no utilizados. Para los demás tipos raíz, el ID. es un valor opaco y debe omitirse.  
  
## <a name="remarks"></a>Notas  
 Las matrices `rootRefIds`, `rootKinds`, `rootFlags`y `rootIds` son matrices paralelas. Es decir, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`y `rootIds[i]` se refieren a la misma raíz.  
  
 Se llama a `RootReferences` y `RootReferences2` para notificar al generador de perfiles. Normalmente, los generadores implementarán un método o el otro, pero no ambos, porque la información pasada en `RootReferences2` es un superconjunto de que se pasa en `RootReferences`.  
  
 Es posible que las entradas de `rootRefIds` sean cero, lo que implica que la referencia raíz correspondiente es NULL y no hace referencia a un objeto en el montón administrado.  
  
 Los identificadores de objeto devueltos por `RootReferences2` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos de direcciones antiguas a direcciones nuevas. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `RootReferences2`. Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , todos los objetos se movieron a sus nuevas ubicaciones y se pueden inspeccionar de forma segura.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](icorprofilercallback2-interface.md)

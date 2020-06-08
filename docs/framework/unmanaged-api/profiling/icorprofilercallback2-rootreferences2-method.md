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
ms.openlocfilehash: 2ce58113f40c8eb67a89b6ab6c9bb8f755975bd5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499758"
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
  
## <a name="parameters"></a>Parámetros  
 `cRootRefs`  
 de El número de elementos de las `rootRefIds` `rootKinds` matrices,, `rootFlags` y `rootIds` .  
  
 `rootRefIds`  
 de Matriz de identificadores de objeto, cada uno de los cuales hace referencia a un objeto estático o a un objeto de la pila. Los elementos de la `rootKinds` matriz proporcionan información para clasificar los elementos correspondientes de la `rootRefIds` matriz.  
  
 `rootKinds`  
 de Matriz de valores de [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) que indican el tipo de la raíz de la recolección de elementos no utilizados.  
  
 `rootFlags`  
 de Matriz de valores de [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) que describen las propiedades de una raíz de recolección de elementos no utilizados.  
  
 `rootIds`  
 de Matriz de valores de UINT_PTR que apuntan a un entero que contiene información adicional sobre la raíz de la recolección de elementos no utilizados, dependiendo del valor del `rootKinds` parámetro.  
  
 Si el tipo de la raíz es una pila, el identificador raíz es para la función que contiene la variable. Si el identificador raíz es 0, la función es una función sin nombre que es interna de CLR. Si el tipo de la raíz es un identificador, el identificador raíz es para el identificador de recolección de elementos no utilizados. Para los demás tipos raíz, el ID. es un valor opaco y debe omitirse.  
  
## <a name="remarks"></a>Comentarios  
 Las `rootRefIds` `rootKinds` matrices,, `rootFlags` y `rootIds` son matrices paralelas. Es decir,,, `rootRefIds[i]` `rootKinds[i]` `rootFlags[i]` y `rootIds[i]` afectan a la misma raíz.  
  
 `RootReferences` `RootReferences2` Se llama a y para notificar al generador de perfiles. Normalmente, los generadores implementarán un método o el otro, pero no ambos, porque la información `RootReferences2` que se pasa es un superconjunto de que se ha pasado `RootReferences` .  
  
 Es posible que las entradas de `rootRefIds` sean cero, lo que implica que la referencia raíz correspondiente es NULL y no hace referencia a un objeto en el montón administrado.  
  
 Los identificadores de objeto devueltos por `RootReferences2` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos de direcciones antiguas a direcciones nuevas. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `RootReferences2`. Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , todos los objetos se movieron a sus nuevas ubicaciones y se pueden inspeccionar de forma segura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (Interfaz)](icorprofilercallback2-interface.md)

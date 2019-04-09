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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09616243aef272be041573864effd25017cc65c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082157"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>ICorProfilerCallback2::RootReferences2 (Método)
Notifica al generador de perfiles sobre las referencias de raíz después de que se ha producido una recolección de elementos. Este método es una extensión de la [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cRootRefs`  
 [in] El número de elementos de la `rootRefIds`, `rootKinds`, `rootFlags`, y `rootIds` matrices.  
  
 `rootRefIds`  
 [in] Una matriz de identificadores de objeto, cada uno de los cuales hace referencia a un objeto estático o un objeto en la pila. Elementos de la `rootKinds` matriz proporcionan información para clasificar los elementos correspondientes en el `rootRefIds` matriz.  
  
 `rootKinds`  
 [in] Una matriz de [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) valores que indican el tipo de la raíz de la colección de elementos no utilizados.  
  
 `rootFlags`  
 [in] Una matriz de [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) valores que describen las propiedades de una raíz de la colección de elementos no utilizados.  
  
 `rootIds`  
 [in] Matriz de UINT_PTR valores que señalan a un entero que contiene información adicional acerca de la raíz de la colección de elementos no utilizados, dependiendo del valor de la `rootKinds` parámetro.  
  
 Si el tipo de la raíz es una pila, es el identificador de la raíz de la función que contiene la variable. Si ese identificador de la raíz es 0, la función es una función sin nombre que es interna al CLR. Si el tipo de la raíz es un identificador, el identificador de la raíz es para el identificador de la colección de elementos no utilizados. Para los tipos de raíz, el identificador es un valor opaco y debe omitirse.  
  
## <a name="remarks"></a>Comentarios  
 El `rootRefIds`, `rootKinds`, `rootFlags`, y `rootIds` son matrices paralelas. Es decir, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, y `rootIds[i]` hacen referencia a la misma raíz.  
  
 Ambos `RootReferences` y `RootReferences2` se llama para notificar al generador de perfiles. Los generadores de perfiles normalmente implementarán un método o la otra, pero no ambos, porque la información pasada `RootReferences2` es un superconjunto de las que pasa `RootReferences`.  
  
 Es posible que las entradas de `rootRefIds` sea cero, lo que implica que la referencia de raíz correspondiente es null y no hace referencia a un objeto en el montón administrado.  
  
 Los identificadores de objeto devuelven por `RootReferences2` no son válidos durante la devolución de llamada, porque podría ser la recolección de elementos en medio de mover objetos de direcciones antiguas a nuevas direcciones. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `RootReferences2`. Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) es llamado, todos los objetos se han movido a sus nuevas ubicaciones y se pueden inspeccionar de manera segura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)

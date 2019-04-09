---
title: ICorProfilerCallback::MovedReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4611b8c186e0293dae73cee4f9d845bb44c167c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073551"
---
# <a name="icorprofilercallbackmovedreferences-method"></a>ICorProfilerCallback::MovedReferences (Método)
Se le llama para informar de la nueva distribución de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cMovedObjectIDRanges`  
 [in] Número de bloques de objetos contiguos que se movieron como resultado de la recolección de elementos no utilizados con compactación. Es decir, el valor de `cMovedObjectIDRanges` es el tamaño total de las matrices `oldObjectIDRangeStart`, `newObjectIDRangeStart` y `cObjectIDRangeLength`.  
  
 Los tres argumentos siguientes de `MovedReferences` son matrices paralelas. En otras palabras, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` y `cObjectIDRangeLength[i]` hacen referencia a un único bloque de objetos contiguos.  
  
 `oldObjectIDRangeStart`  
 [in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial antigua (antes de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.  
  
 `newObjectIDRangeStart`  
 [in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial nueva (después de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.  
  
 `cObjectIDRangeLength`  
 [in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque de objetos contiguos en la memoria.  
  
 Se especifica un tamaño para cada bloque al que se hace referencia en las matrices `oldObjectIDRangeStart` y `newObjectIDRangeStart`.  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
>  Este método notifica tamaños como `MAX_ULONG` para objetos de más de 4 GB en plataformas de 64 bits. Para obtener el tamaño de los objetos que son mayores de 4 GB, use el [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) método en su lugar.  
  
 Un recolector de elementos no utilizados con compactación recupera la memoria ocupada por los objetos inactivos y compacta ese espacio liberado. Como resultado, los objetos activos podrían moverse dentro del montón y los valores de `ObjectID` distribuidos por notificaciones anteriores podrían cambiar.  
  
 Supongamos que un valor `ObjectID` existente (`oldObjectID`) se encuentra dentro del intervalo siguiente:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 En este caso, el desplazamiento desde el inicio del intervalo al inicio del objeto es el siguiente:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Para cualquier valor de `i` que esté en el intervalo siguiente:  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 puede calcular el nuevo `ObjectID` de la siguiente manera:  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)  
  
 Ninguno de los valores `ObjectID` pasados por `MovedReferences` son válidos durante la devolución de llamada en sí porque el recolector de elementos no utilizados puede estar en proceso de mover objetos de ubicaciones anteriores a nuevas. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `MovedReferences`. Un [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) devolución de llamada indica que todos los objetos se han movido a sus nuevas ubicaciones y se puede realizar la inspección.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Método MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)

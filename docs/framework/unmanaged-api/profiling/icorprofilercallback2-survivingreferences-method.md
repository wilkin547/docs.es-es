---
title: ICorProfilerCallback2::SurvivingReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.SurvivingReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type:
- apiref
ms.openlocfilehash: 3681106bca94f1fefb2f24a1aa4254eb2b1b0531
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499745"
---
# <a name="icorprofilercallback2survivingreferences-method"></a>ICorProfilerCallback2::SurvivingReferences (Método)
Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cSurvivingObjectIDRanges`  
 [in] Número de bloques de objetos contiguos que sobrevivieron como resultado de la recolección de elementos no utilizados sin compactación. Es decir, el valor de `cSurvivingObjectIDRanges` es el tamaño de las matrices `objectIDRangeStart` y `cObjectIDRangeLength`, que almacenan un `ObjectID` y una longitud, respectivamente, para cada bloque de objetos.  
  
 Los dos argumentos siguientes de `SurvivingReferences` son matrices paralelas. En otras palabras, `objectIDRangeStart` y `cObjectIDRangeLength` hacen referencia al mismo bloque de objetos contiguos.  
  
 `objectIDRangeStart`  
 [in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial de un bloque de objetos activos y contiguos en la memoria.  
  
 `cObjectIDRangeLength`  
 [in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque superviviente de objetos contiguos en la memoria.  
  
 Se especifica un tamaño para cada bloque al que se hace referencia en la matriz `objectIDRangeStart`.  
  
## <a name="remarks"></a>Comentarios  
  
> [!IMPORTANT]
> Este método notifica tamaños como `MAX_ULONG` para objetos de más de 4 GB en plataformas de 64 bits. En el caso de objetos mayores de 4 GB, use el método [ICorProfilerCallback4:: survivingreferences2 (](icorprofilercallback4-survivingreferences2-method.md) en su lugar.  
  
 Los elementos de las matrices `objectIDRangeStart` y `cObjectIDRangeLength` deben interpretarse del siguiente modo para determinar si un objeto ha sobrevivido a la recolección de elementos no utilizados. Supongamos que un valor `ObjectID` (`ObjectID`) se encuentra dentro del intervalo siguiente:  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 Para cualquier valor `i` que esté en el intervalo siguiente, el objeto sobrevivió a la recolección de elementos no utilizados:  
  
 0 <=`i` < `cSurvivingObjectIDRanges`  
  
 Una recolección de elementos no utilizados sin compactación recupera la memoria ocupada por objetos "inactivos", pero no compacta ese espacio liberado. Como consecuencia, la memoria se devuelve al montón pero no se mueve ningún objeto "activo".  
  
 Common Language Runtime (CLR) llama a `SurvivingReferences` para las recolecciones de elementos no utilizados sin compactación. Para compactar las recolecciones de elementos no utilizados, se llama a [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) en su lugar. Se puede compactar una única recolección de elementos no utilizados para una generación y no compactar para otra. Para una recolección de elementos no utilizados en una generación determinada, el generador de perfiles recibirá una devolución de llamada `SurvivingReferences` o una devolución de llamada `MovedReferences`, pero no ambas.  
  
 Se pueden recibir varias devoluciones de llamada `SurvivingReferences` durante una recolección de elementos no utilizados determinada debido a un almacenamiento en búfer interno limitado, a la notificación de varios subprocesos en el caso de la recolección de elementos no utilizados de servidor, y a otros motivos. En el caso de varias devoluciones de llamada durante una recolección de elementos no utilizados, la información es acumulativa. Todas las referencias que se notifican en cualquier devolución de llamada `SurvivingReferences` sobreviven a la recolección de elementos no utilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (Interfaz)](icorprofilercallback2-interface.md)
- [Método SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md)

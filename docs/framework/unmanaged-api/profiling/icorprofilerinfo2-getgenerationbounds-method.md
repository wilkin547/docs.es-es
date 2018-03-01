---
title: "ICorProfilerInfo2::GetGenerationBounds (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c84be5d7e78c348c0368e9639a470a8fc60e2ca7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a>ICorProfilerInfo2::GetGenerationBounds (Método)
Obtiene las regiones de memoria, que son segmentos del montón, que componen las distintas generaciones de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cObjectRanges`  
 [in] Número de elementos asignado por el llamador para la matriz `ranges`.  
  
 `pcObjectRanges`  
 [out] Puntero a un entero que especifica el número total de intervalos, de los que algunos o todos se devolverán en la matriz `ranges`.  
  
 `ranges`  
 [out] Una matriz de [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructuras, cada uno de los cuales describe un intervalo (es decir, un bloque) de memoria en la generación que se está sometiendo a la recolección de elementos.  
  
## <a name="remarks"></a>Comentarios  
 Se puede llamar al método `GetGenerationBounds` desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso. Es decir, se puede llamar desde cualquier devolución de llamada excepto las que se producen entre [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) y [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).  
  
 La mayoría de los cambios de generación tienen lugar durante las recolecciones de elementos no utilizados. Las generaciones pueden crecer de una recolección a otra, pero por lo general no se mueven. Por este motivo, los lugares más interesantes para llamar a `GetGenerationBounds` están en `ICorProfilerCallback2::GarbageCollectionStarted` y `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
 Durante el inicio del programa, algunos objetos son asignados por el propio Common Language Runtime (CLR), por lo general en las generaciones 3 y 0. Por lo tanto, en el momento en que se inicia la ejecución del código administrado, estas generaciones ya contendrán objetos. Las generaciones 1 y 2 normalmente estarán vacías, salvo por los objetos ficticios generados por el recolector de elementos no utilizados. (El tamaño de los objetos ficticios es de 12 bytes en las implementaciones de 32 bits de CLR; el tamaño es mayor en las implementaciones de 64 bits). Puede que también vea intervalos de generación 2 dentro de los módulos producidos por el generador de imágenes nativas (NGen.exe). En este caso, los objetos de la generación 2 son *objetos inmovilizados*, que se asignan cuando se ejecuta NGen.exe en lugar de por el recolector de elementos no utilizados.  
  
 Esta función usa búferes asignados por el llamador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)

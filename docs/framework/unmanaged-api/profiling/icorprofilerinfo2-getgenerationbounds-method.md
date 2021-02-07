---
description: 'Más información acerca de: ICorProfilerInfo2:: Getgenerationbounds ((método)'
title: ICorProfilerInfo2::GetGenerationBounds (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 2f6fb9037be2722166653cceb4081a5ddcb81327
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753233"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a>ICorProfilerInfo2::GetGenerationBounds (Método)

Obtiene las regiones de memoria, que son segmentos del montón, que componen las distintas generaciones de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cObjectRanges`  
 [in] Número de elementos asignado por el llamador para la matriz `ranges`.  
  
 `pcObjectRanges`  
 [out] Puntero a un entero que especifica el número total de intervalos, de los que algunos o todos se devolverán en la matriz `ranges`.  
  
 `ranges`  
 enuncia Matriz de estructuras de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , cada una de las cuales describe un intervalo (es decir, un bloque) de memoria dentro de la generación que está en proceso de recolección de elementos no utilizados.  
  
## <a name="remarks"></a>Observaciones  

 Se puede llamar al método `GetGenerationBounds` desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso.

 La mayoría de los cambios de generación tienen lugar durante las recolecciones de elementos no utilizados. Las generaciones pueden crecer de una recolección a otra, pero por lo general no se mueven. Por este motivo, los lugares más interesantes para llamar a `GetGenerationBounds` están en `ICorProfilerCallback2::GarbageCollectionStarted` y `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
 Durante el inicio del programa, algunos objetos son asignados por el propio Common Language Runtime (CLR), por lo general en las generaciones 3 y 0. Por lo tanto, en el momento en que se inicia la ejecución del código administrado, estas generaciones ya contendrán objetos. Las generaciones 1 y 2 normalmente estarán vacías, salvo por los objetos ficticios generados por el recolector de elementos no utilizados. (El tamaño de los objetos ficticios es de 12 bytes en las implementaciones de 32 bits de CLR; el tamaño es mayor en las implementaciones de 64 bits). También puede ver intervalos de generación 2 que se encuentran dentro de módulos generados por el generador de imágenes nativas (NGen.exe). En este caso, los objetos de la generación 2 son *objetos inmovilizados*, que se asignan cuando NGen.exe se ejecuta en lugar del recolector de elementos no utilizados.  
  
 Esta función usa búferes asignados por el llamador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

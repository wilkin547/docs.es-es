---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 4b13659f7c9909e9795caee1eace8da8092c5b9a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974035"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10:: EnumerateObjectReferences (método)
  
 Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).   
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```  
  
#### <a name="parameters"></a>Parámetros  

 `objectId` \
 de Objeto en el que se van a enumerar las referencias.

 `callback` \
 de Función a la que se llamará con las referencias para el objeto.

 `clientData` \
 de Datos proporcionados por el generador de perfiles `callback` que se van a pasar a la función.
  
## <a name="remarks"></a>Comentarios  
 El `EnumerateObjectReferences` método es similar a [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), con la salvedad de que recorre las referencias a petición para el generador de perfiles en lugar de asignar previamente una matriz para almacenar las referencias.  

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]
  
## <a name="see-also"></a>Vea también
- [Interfaz ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)


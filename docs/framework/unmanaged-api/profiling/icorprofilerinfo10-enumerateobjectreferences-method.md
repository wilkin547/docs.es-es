---
description: 'Más información sobre: ICorProfilerInfo10:: EnumerateObjectReferences (método)'
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
ms.openlocfilehash: bcd374aec2944977a0745177995ba8adf0cce9b7
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759422"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10:: EnumerateObjectReferences (método)

Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>Parámetros

`objectId` de Objeto en el que se van a enumerar las referencias.

`callback` de Función a la que se llamará con las referencias para el objeto.

`clientData` de Datos proporcionados por el generador de perfiles que se van a pasar a la `callback` función.

## <a name="remarks"></a>Observaciones

El `EnumerateObjectReferences` método es similar a [ObjectReferences](icorprofilercallback-objectreferences-method.md), con la salvedad de que recorre las referencias a petición para el generador de perfiles en lugar de asignar previamente una matriz para almacenar las referencias.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaz ICorProfilerInfo10](icorprofilerinfo10-interface.md)

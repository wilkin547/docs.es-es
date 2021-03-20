---
description: 'Más información sobre: ICorProfilerInfo10:: IsFrozenObject (método)'
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: c4d31c96fd7470a153437ffb0125e81ca8ea77bd
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759760"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a>ICorProfilerInfo10:: IsFrozenObject (método)

Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a>Parámetros

`objectId` de Objeto que se va a examinar.

`pbFrozen` enuncia Un valor de `BOOL` tipo que indica si el objeto está en un segmento de solo lectura.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaz ICorProfilerInfo10](icorprofilerinfo10-interface.md)

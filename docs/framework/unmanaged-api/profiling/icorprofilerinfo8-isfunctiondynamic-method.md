---
description: 'Más información sobre: ICorProfilerInfo8:: IsFunctionDynamic (método)'
title: ICorProfilerInfo8::IsFunctionDynamic
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 139edeed3e078668974382f1719c8e03f83e2a09
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759083"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>ICorProfilerInfo8:: IsFunctionDynamic (método)

Determina si una función no tiene metadatos asociados.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a>Parámetros

`functionId` de  `FunctionID` Que identifica la función en cuestión.

`isDynamic` enuncia Un puntero a un `BOOL` que contendrá un valor que indica si la función no tiene metadatos.

## <a name="remarks"></a>Observaciones

Una función se considera dinámica si no tiene metadatos. Ciertos métodos como el código auxiliar de IL o los métodos LCG no tienen metadatos asociados que se pueden recuperar mediante las API de IMetaDataImport. Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando a [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Consulte también

- [Interface ICorProfilerInfo8](icorprofilerinfo8-interface.md)

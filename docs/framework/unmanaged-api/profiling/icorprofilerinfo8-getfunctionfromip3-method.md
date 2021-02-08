---
description: 'Más información sobre: ICorProfilerInfo8:: GetFunctionFromIP3 (método)'
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3ce0a0964e26254ab09e515826b6bceb657e07bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783838"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>ICorProfilerInfo8:: GetFunctionFromIP3 (método)

Asigna un puntero de instrucción de código administrado a un FunctionID. Este método funciona para los métodos dinámicos y no dinámicos.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a>Parámetros

- `ip`

  \[in] el puntero de instrucción en código administrado.

- `pFunctionId`

  \[out] el identificador de la función.

- `pReJitId`

  \[out] la identidad de la versión recompilada con JIT de la función.

## <a name="remarks"></a>Observaciones

Este método funciona para los métodos dinámicos y no dinámicos. Es un supraconjunto de [getfunctionfromip2 (](icorprofilerinfo4-getfunctionfromip2-method.md), que solo funciona con funciones con metadatos.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [Interface ICorProfilerInfo8](icorprofilerinfo8-interface.md)

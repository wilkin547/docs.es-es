---
description: 'Más información sobre: ICorProfilerInfo9:: GetNativeCodeStartAddresses (método)'
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 062aebf6d5bed208ea71b215bd9f857b82483673
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759056"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>ICorProfilerInfo9:: GetNativeCodeStartAddresses (método)

Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a>Parámetros

`functionId` de IDENTIFICADOR de la función cuyas direcciones de inicio de código nativo deben devolverse.

`reJitId` de La identidad de la función con compilación JIT.

`cCodeStartAddresses` de Tamaño máximo de la `codeStartAddresses` matriz.

`pcCodeStartAddresses` enuncia El número de direcciones disponibles.

`codeStartAddresses` enuncia Una matriz de `UINT_PTR` , cada una de las cuales es la dirección inicial de un cuerpo nativo para la función especificada.

## <a name="remarks"></a>Observaciones

Cuando la compilación en capas está habilitada, una función puede tener más de un cuerpo de código nativo.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:**[!INCLUDE[net_core_21](../../../../includes/net-core-21-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaz ICorProfilerInfo9](icorprofilerinfo9-interface.md)

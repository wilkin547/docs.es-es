---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 9e8e4c7e6c367970100c98dc3dc8237b25f99221
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665601"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a>ICorProfilerInfo9:: GetILToNativeMapping3 (método)

Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

#### <a name="parameters"></a>Parámetros

`pNativeCodeStartAddress` \
de Puntero al inicio de una función nativa.

`cMap` \
[in] Tamaño máximo de la matriz `map`.

`pcMap` \
enuncia Número total de estructuras COR_DEBUG_IL_TO_NATIVE_MAP disponibles.

`map` \
enuncia Una matriz de estructuras [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , cada una de las cuales especifica los desplazamientos. Después de que el método `GetILToNativeMapping3` vuelva, `map` contendrá algunas o todas las estructuras `COR_DEBUG_IL_TO_NATIVE_MAP`.

## <a name="remarks"></a>Comentarios

Cuando la compilación en capas está habilitada, un método puede tener más de un cuerpo de código nativo. [ICorProfilerInfo9:: GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) devolverá las direcciones de inicio para todos los cuerpos de código nativo.

## <a name="requirements"></a>Requisitos

**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Encabezado**: Corprof. idl, Corprof. h

**Biblioteca** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

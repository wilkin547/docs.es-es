---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: e6708971909c1035e41786f4d8dad1cf9afdffaf
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665616"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>ICorProfilerInfo9:: GetCodeInfo4 (método)

Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a>Parámetros

`pNativeCodeStartAddress` \
de Puntero al inicio de una función nativa.

`cCodeInfos` \
[in] Tamaño de la matriz `codeInfos`.

`pcCodeInfos` \
enuncia Un puntero al número total de estructuras [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) disponibles.

`codeInfos` \
[out] Búfer proporcionado por el llamador. Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.

## <a name="remarks"></a>Comentarios

El `GetCodeInfo4` método es similar a [getcodeinfo3 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), con la salvedad de que puede buscar información de código para diferentes versiones nativas de un método.

> [!NOTE]
> `GetCodeInfo4`puede desencadenar una recolección de elementos no utilizados.

Las extensiones se clasifican en orden creciente de desplazamiento de Common Intermediate Language (CIL).

Después `GetCodeInfo4` de que devuelva, debe comprobar `codeInfos` que el búfer era lo suficientemente grande como para contener todas las estructuras [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) . Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`. Si `cCodeInfos` dividido por el tamaño de una estructura [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) es menor que `pcCodeInfos`, asigne un búfer `codeInfos` mayor, actualice `cCodeInfos` con el nuevo tamaño mayor y vuelva a llamar `GetCodeInfo4` a.

También tiene la opción de llamar primero a `GetCodeInfo4` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el tamaño del búfer `codeInfos` en el valor devuelto en `pcCodeInfos`, multiplicado por el tamaño de una estructura [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) y volver a llamar a `GetCodeInfo4`.

## <a name="requirements"></a>Requisitos

**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).

**Encabezado**: Corprof. idl, Corprof. h

**Biblioteca** CorGuids.lib

**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)

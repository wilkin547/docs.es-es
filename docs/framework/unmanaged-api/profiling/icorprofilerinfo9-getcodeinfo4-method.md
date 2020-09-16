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
ms.openlocfilehash: ecaff179378eb417393c0a0d17d0a00d3b99e5a4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541303"
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

## <a name="parameters"></a>Parámetros

- `pNativeCodeStartAddress`

  \[in] un puntero al inicio de una función nativa.

- `cCodeInfos`

  \[en] tamaño de la `codeInfos` matriz.

- `pcCodeInfos`

  \[out] un puntero al número total de estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibles.

- `codeInfos`

  \[out] un búfer proporcionado por el autor de la llamada. Después de que el método vuelva, contiene una matriz de estructuras `COR_PRF_CODE_INFO`, cada una de las cuales describe un bloque de código nativo.

## <a name="remarks"></a>Comentarios

El `GetCodeInfo4` método es similar a [getcodeinfo3 (](icorprofilerinfo4-getcodeinfo3-method.md), con la salvedad de que puede buscar información de código para diferentes versiones nativas de un método.

> [!NOTE]
> `GetCodeInfo4` puede desencadenar una recolección de elementos no utilizados.

Las extensiones se clasifican en orden creciente de desplazamiento de Common Intermediate Language (CIL).

Después de `GetCodeInfo4` que devuelva, debe comprobar que el `codeInfos` búfer era lo suficientemente grande como para contener todas las estructuras de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) . Para ello, compare el valor de `cCodeInfos` con el valor del parámetro `cchName`. Si `cCodeInfos` se divide por el tamaño de una estructura de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) es menor que `pcCodeInfos` , asigne un `codeInfos` búfer mayor, actualice `cCodeInfos` con el nuevo tamaño mayor y vuelva a llamar a `GetCodeInfo4` .

También tiene la opción de llamar primero a `GetCodeInfo4` con un búfer `codeInfos` de longitud de cero para obtener el tamaño de búfer correcto. Después, puede establecer el `codeInfos` tamaño del búfer en el valor devuelto en `pcCodeInfos` , multiplicado por el tamaño de una estructura de [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) y volver a llamar a `GetCodeInfo4` .

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo9](ICorProfilerInfo9-interface.md)

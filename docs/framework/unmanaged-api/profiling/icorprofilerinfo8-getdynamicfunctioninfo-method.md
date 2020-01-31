---
title: ICorProfilerInfo8::GetDynamicFunctionInfo
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 66a08cf60ae4ca9bb6e373d230d0819ee6f9b28c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790007"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>ICorProfilerInfo8:: GetDynamicFunctionInfo (método)

Recupera información acerca de los métodos dinámicos.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a>Parameters

- `functionId`

  \[en] identificador de la función para la que se va a recuperar información.

- `moduleId`

  \[en] un puntero al módulo en el que se define la clase primaria de la función.

- `ppvSig`

  \[out] un puntero a la firma de la función.

- `pbSig`

  \[out] un puntero al recuento de bytes para la firma de la función.

- `cchName`

  \[en] el tamaño máximo de la matriz de `wszName`.

- `pcchName`

  \[out] número de caracteres de la matriz de `wszName`.

- `wszName`

  \[out] una matriz de `WCHAR` que es el nombre de la función, si existe.

## <a name="remarks"></a>Notas

Ciertos métodos como código auxiliar de IL o LCG no tienen metadatos asociados que se pueden recuperar mediante las API [IMetaDataImport](../metadata/imetadataimport-interface.md) y [IMetaDataImport2](../metadata/imetadataimport2-interface.md) . Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

Esta API se puede usar para recuperar información acerca de los métodos dinámicos, incluido un nombre descriptivo, si está disponible.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** CorProf.idl, CorProf.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

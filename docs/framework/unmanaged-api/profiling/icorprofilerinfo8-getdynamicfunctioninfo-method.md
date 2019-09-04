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
ms.openlocfilehash: 45a40d49cea2dd5f881fbd47cc2fb4bd96e8f9ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243984"
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

#### <a name="parameters"></a>Parámetros

`functionId` \
de IDENTIFICADOR de la función para la que se va a recuperar información.

`moduleId` \
de Puntero al módulo en el que se define la clase primaria de la función.

`ppvSig` \
enuncia Puntero a la firma de la función.

`pbSig` \
enuncia Puntero al recuento de bytes para la firma de la función.

`cchName` \
[in] Tamaño máximo de la matriz `wszName`.

`pcchName` \
enuncia Número de caracteres de la `wszName` matriz.

`wszName` \
enuncia Matriz de `WCHAR` que es el nombre de la función, si existe.

## <a name="remarks"></a>Comentarios

Ciertos métodos como código auxiliar de IL o LCG no tienen metadatos asociados que se pueden recuperar mediante las API [IMetaDataImport](../metadata/imetadataimport-interface.md) y [IMetaDataImport2](../metadata/imetadataimport2-interface.md) . Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

Esta API se puede usar para recuperar información acerca de los métodos dinámicos, incluido un nombre descriptivo, si está disponible.

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: Corprof. idl, Corprof. h

**Biblioteca** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

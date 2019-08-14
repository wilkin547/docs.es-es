---
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
ms.openlocfilehash: 71c4e749368dce65d5250b9ab78fd8713e9d61a0
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973875"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>ICorProfilerInfo8:: IsFunctionDynamic (método)
  
  Determina si una función no tiene metadatos asociados.    
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId` \
  de  `FunctionID` Que identifica la función en cuestión.

  `isDynamic` \
  enuncia Un puntero a un `BOOL` que contendrá un valor que indica si la función no tiene metadatos.

## <a name="remarks"></a>Comentarios  
 Una función se considera dinámica si no tiene metadatos. Ciertos métodos como el código auxiliar de IL o los métodos LCG no tienen metadatos asociados que se pueden recuperar mediante las API de IMetaDataImport. Estos métodos pueden ser detectados por los profileres a través de punteros de instrucción o escuchando a [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **.NET Framework versiones:** [! INCLUIR[net_current_v472plus](../../../../includes/net-current-v472plus.md)  
  
## <a name="see-also"></a>Vea también
- [Interfaz ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)


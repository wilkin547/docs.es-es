---
title: ICorProfilerInfo3::GetFunctionEnter3Info (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 7e93b92b0b0b4c44955ebc7dfb9d1eb875713c27
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449724"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a>ICorProfilerInfo3::GetFunctionEnter3Info (Método)
Proporciona el marco de pila y la información de los argumentos de la función que se está informando al generador de perfiles mediante la función [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) . Solo se puede llamar a este método durante la devolución de llamada `FunctionEnter3WithInfo`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] `FunctionID` de la función que se está especificando.  
  
 `eltInfo`  
 [in] Controlador opaco que representa información sobre un marco de pila determinado. El generador de perfiles debe proporcionar el mismo `eltInfo` que proporcionó la función [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) .  
  
 `pFrameInfo`  
 [out] Controlador opaco que representa información genérica sobre un marco de pila determinado. Este identificador es válido solo durante la devolución de llamada `FunctionEnter3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionEnter3Info`.  
  
 `pcbArgumentInfo`  
 [in, out] Puntero al tamaño total, en bytes, de la estructura de [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) (más las estructuras de [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) adicionales para los intervalos de argumentos a los que apunta `pArgumentInfo`). Si el tamaño especificado no es suficiente, se devuelve ERROR_INSUFFICIENT_BUFFER y el tamaño esperado se almacena en `pcbArgumentInfo`. Para llamar a `GetFunctionEnter3Info` para recuperar el valor de `*pcbArgumentInfo` esperado, establezca `*pcbArgumentInfo`=0 y `pArgumentInfo`=NULL.  
  
 `pArgumentInfo`  
 enuncia Puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) que describe las ubicaciones de los argumentos de la función en la memoria, en orden de izquierda a derecha.  
  
## <a name="remarks"></a>Comentarios  
 El generador de perfiles debe asignar espacio suficiente para la estructura `COR_PRF_FUNCTION_ARGUMENT_INFO` de la función que se está inspeccionando y debe indicar el tamaño del parámetro `pcbArgumentInfo`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)

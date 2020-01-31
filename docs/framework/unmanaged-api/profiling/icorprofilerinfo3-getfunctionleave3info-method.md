---
title: ICorProfilerInfo3::GetFunctionLeave3Info (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
ms.openlocfilehash: 0d3b93a293d4dda9dfe7b576708c832de2e25869
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862410"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a>ICorProfilerInfo3::GetFunctionLeave3Info (Método)
Proporciona el marco de pila y el valor devuelto de la función que se está informando al generador de perfiles mediante la función de [función FunctionLeave3WithInfo](functionleave3withinfo-function.md) . Solo se puede llamar a este método durante la devolución de llamada `FunctionLeave3WithInfo`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 de `FunctionID` de la función que se devuelve.  
  
 `eltInfo`  
 [in] Controlador opaco que representa información sobre un marco de pila determinado. El generador de perfiles debe proporcionar el mismo `eltInfo` que ha proporcionado el generador de perfiles mediante la función [FunctionLeave3WithInfo](functionleave3withinfo-function.md) .  
  
 `pFrameInfo`  
 [out] Controlador opaco que representa información genérica sobre un marco de pila determinado. Este identificador es válido solo durante la devolución de llamada `FunctionLeave3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionLeave3Info`.  
  
 `pRetvalRange`  
 enuncia Puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) que contiene el valor devuelto de la función. Para tener acceso a la información del valor devuelto, se debe establecer la marca `COR_PRF_ENABLE_FUNCTION_RETVAL`. El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.  
  
## <a name="remarks"></a>Notas  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3 (interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

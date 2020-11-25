---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: a7272d55771620db129125ce543d12d19a0b4dfb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697849"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a>ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)

Especifica las funciones implementadas por el generador de perfiles a las que se llamará en las funciones [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pFuncEnter3`  
 de Puntero a la implementación de que se va a utilizar como `FunctionEnter3` devolución de llamada.  
  
 `pFuncLeave3`  
 de Puntero a la implementación de que se va a utilizar como `FunctionLeave3` devolución de llamada.  
  
 `pFuncTailcall3`  
 de Puntero a la implementación de que se va a utilizar como `FunctionTailcall3` devolución de llamada.  
  
## <a name="remarks"></a>Comentarios  

 Los enlaces [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) no proporcionan el marco de pila y la inspección de argumentos. Para tener acceso a esa información `COR_PRF_ENABLE_FUNCTION_ARGS` , `COR_PRF_ENABLE_FUNCTION_RETVAL` se deben establecer las marcas,, y/o  `COR_PRF_ENABLE_FRAME_INFO` . El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el método [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.  
  
 Solo un conjunto de devoluciones de llamada puede estar activo a la vez y la versión más reciente tiene prioridad. Por lo tanto, si un generador de perfiles llama al [método SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y al `SetEnterLeaveFunctionHooks3` método, `SetEnterLeaveFunctionHooks3` se usa.  
  
 `SetEnterLeaveFunctionHooks3`Solo se puede llamar al método desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Setenterleavefunctionhooks3withinfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
- [ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

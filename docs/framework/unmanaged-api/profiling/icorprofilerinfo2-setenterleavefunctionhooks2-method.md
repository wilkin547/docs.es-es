---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
ms.openlocfilehash: 7eac42e1d8132ca9e6d6c6b43efd43b88c1e5d3d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868595"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)
Especifica las funciones implementadas por el generador de perfiles a las que se va a llamar en las versiones actualizadas de los enlaces "Enter", "Leave" y "llamada" de las funciones administradas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parameters  
 `pFuncEnter`  
 de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionEnter2](functionenter2-function.md) .  
  
 `pFuncLeave`  
 de Un puntero a la implementación de que se va a usar como devolución de llamada de [FunctionLeave2](functionleave2-function.md) .  
  
 `pFuncTailcall`  
 de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionTailcall2](functiontailcall2-function.md) .  
  
## <a name="remarks"></a>Notas  
 El método `SetEnterLeaveFunctionHooks2` es similar al método [ICorProfilerInfo:: SetEnterLeaveFunctionHooks (](icorprofilerinfo-setenterleavefunctionhooks-method.md) . Use el primero para especificar las funciones que se van a usar como las versiones más recientes de las devoluciones de llamada Enter/Leave/llamada y la última para especificar las funciones que se van a usar como versiones anteriores de las devoluciones de llamada Enter/Leave/llamada.  
  
 Solo un conjunto de devoluciones de llamada puede estar activo a la vez. Por lo tanto, si un generador de perfiles llama a `ICorProfilerInfo::SetEnterLeaveFunctionHooks` y `SetEnterLeaveFunctionHooks2`, se usa `SetEnterLeaveFunctionHooks2`.  
  
 Solo se puede llamar al método `SetEnterLeaveFunctionHooks2` desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)

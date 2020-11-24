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
ms.openlocfilehash: f71d0b5c77d4a514001bcbe6904ed912be388d18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681553"
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
  
## <a name="parameters"></a>Parámetros  

 `pFuncEnter`  
 de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionEnter2](functionenter2-function.md) .  
  
 `pFuncLeave`  
 de Un puntero a la implementación de que se va a usar como devolución de llamada de [FunctionLeave2](functionleave2-function.md) .  
  
 `pFuncTailcall`  
 de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionTailcall2](functiontailcall2-function.md) .  
  
## <a name="remarks"></a>Comentarios  

 El `SetEnterLeaveFunctionHooks2` método es similar al método [ICorProfilerInfo:: SetEnterLeaveFunctionHooks (](icorprofilerinfo-setenterleavefunctionhooks-method.md) . Use el primero para especificar las funciones que se van a usar como las versiones más recientes de las devoluciones de llamada Enter/Leave/llamada y la última para especificar las funciones que se van a usar como versiones anteriores de las devoluciones de llamada Enter/Leave/llamada.  
  
 Solo un conjunto de devoluciones de llamada puede estar activo a la vez. Por lo tanto, si un generador de perfiles llama a `ICorProfilerInfo::SetEnterLeaveFunctionHooks` y `SetEnterLeaveFunctionHooks2` , `SetEnterLeaveFunctionHooks2` se utiliza.  
  
 `SetEnterLeaveFunctionHooks2`Solo se puede llamar al método desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)

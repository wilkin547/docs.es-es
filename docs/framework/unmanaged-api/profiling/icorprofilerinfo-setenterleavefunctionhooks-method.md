---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: 45593e7e30e1c8f8036489936aab3c607b01dd52
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438647"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks (Método)
Especifica las funciones implementadas por el generador de perfiles a las que se llamará en los enlaces "Enter", "Leave" y "llamada" de las funciones administradas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pFuncEnter`  
 de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionEnter (](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) .  
  
 `pFuncLeave`  
 de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionLeave (](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) .  
  
 `pFuncTailcall`  
 de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionTailcall (](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) .  
  
## <a name="remarks"></a>Comentarios  
 En la versión .NET Framework 1,0, cada puntero de función puede ser null para deshabilitar la devolución de llamada correspondiente.  
  
 Solo un conjunto de devoluciones de llamada puede estar activo a la vez. Por lo tanto, si un generador de perfiles llama a `SetEnterLeaveFunctionHooks` e [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), `SetEnterLeaveFunctionHooks2` tiene prioridad.  
  
 Solo se puede llamar al método `SetEnterLeaveFunctionHooks` desde la devolución de llamada [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) del generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

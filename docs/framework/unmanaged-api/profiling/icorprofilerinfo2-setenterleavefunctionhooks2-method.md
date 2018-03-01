---
title: "ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c460cfd24a83ca2a6c75e061b7a797c8f455bc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)
Especifica las funciones implementadas por el generador de perfiles que se llame en las versiones actualizadas de los "Entrar", "leave" y "tailcall" enlaces de funciones administradas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pFuncEnter`  
 [in] Un puntero a la implementación que se usará como el [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) devolución de llamada.  
  
 `pFuncLeave`  
 [in] Un puntero a la implementación que se usará como el [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) devolución de llamada.  
  
 `pFuncTailcall`  
 [in] Un puntero a la implementación que se usará como el [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) devolución de llamada.  
  
## <a name="remarks"></a>Comentarios  
 El `SetEnterLeaveFunctionHooks2` método es similar a la [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) método. Utilice el primero para especificar las funciones que se usará como las versiones más recientes de las devoluciones de llamada ENTRAR/leave/tailcall y el segundo para especificar las funciones que se usará como las versiones anteriores de las devoluciones de llamada ENTRAR/leave/tailcall.  
  
 Un conjunto de devoluciones de llamada no se activa cada vez. Por lo tanto, si llama a un generador de perfiles las `ICorProfilerInfo::SetEnterLeaveFunctionHooks` y `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` se utiliza.  
  
 El `SetEnterLeaveFunctionHooks2` solo desde el generador de perfiles puede llamar al método [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

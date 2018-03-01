---
title: "FunctionLeave2 (Función)"
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
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86ffb6cc18de0b0b7b68b418477c1e8cdd6e6cc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave2-function"></a>FunctionLeave2 (Función)
Notifica al generador de perfiles que una función se va a devolver al llamador y proporciona información sobre el valor de retorno de marco y la función de pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `funcId`  
 [in] El identificador de la función que devuelve.  
  
 `clientData`  
 [in] El identificador de la función reasignada, que el generador de perfiles especificó previamente a través de la [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) función.  
  
 `func`  
 [in] Un `COR_PRF_FRAME_INFO` valor que indica dónde obtener información sobre el marco de pila.  
  
 El generador de perfiles debe tratar como un identificador opaco que puede pasarse al motor de ejecución en el [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) método.  
  
 `retvalRange`  
 [in] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) estructura que especifica la ubicación de memoria del valor devuelto por la función.  
  
 Para tener acceso a información del valor devuelto, el `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca. Puede usar el generador de perfiles la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer las marcas de evento.  
  
## <a name="remarks"></a>Comentarios  
 Los valores de la `func` y `retvalRange` parámetros no son válidos después de la `FunctionLeave2` función devuelve porque los valores pueden cambiar o destruirlos.  
  
 El `FunctionLeave2` función es una devolución de llamada; debe implementar. La implementación debe utilizar el `__declspec`(`naked`) el atributo de clase de almacenamiento.  
  
 El motor de ejecución no guardan los registros antes de llamar a esta función.  
  
-   En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
-   Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.  
  
 La implementación de `FunctionLeave2` no debe bloquearse porque retrasará la recolección de elementos. La implementación no debería intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados. Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionLeave2` devuelve.  
  
 Además, la `FunctionLeave2` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)

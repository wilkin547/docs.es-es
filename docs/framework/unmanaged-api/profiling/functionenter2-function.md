---
title: FunctionEnter2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d79249a2540adbd7f1b7e9bf36c899ba94d71e2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452395"
---
# <a name="functionenter2-function"></a>FunctionEnter2 (Función)
Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre la pila de argumentos de marco y la función. Esta función reemplaza la [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `funcId`  
 [in] El identificador de la función a la que se pasa el control.  
  
 `clientData`  
 [in] El identificador de la función reasignada, que el generador de perfiles especificó previamente mediante el [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) función.  
  
 `func`  
 [in] Un `COR_PRF_FRAME_INFO` valor que indica dónde obtener información sobre el marco de pila.  
  
 El generador de perfiles debe tratar como un identificador opaco que puede pasarse al motor de ejecución en el [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) método.  
  
 `argumentInfo`  
 [in] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) estructura que especifica las ubicaciones de memoria de los argumentos de función.  
  
 Para tener acceso a información del argumento, el `COR_PRF_ENABLE_FUNCTION_ARGS` se debe establecer la marca. Puede usar el generador de perfiles la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer las marcas de evento.  
  
## <a name="remarks"></a>Comentarios  
 Los valores de la `func` y `argumentInfo` parámetros no son válidos después de la `FunctionEnter2` función devuelve porque los valores pueden cambiar o destruirlos.  
  
 El `FunctionEnter2` función es una devolución de llamada; debe implementar. La implementación debe utilizar el `__declspec`(`naked`) el atributo de clase de almacenamiento.  
  
 El motor de ejecución no guardan los registros antes de llamar a esta función.  
  
-   En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
-   Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.  
  
 La implementación de `FunctionEnter2` no debe bloquearse porque retrasará la recolección de elementos. La implementación no debería intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados. Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionEnter2` devuelve.  
  
 Además, la `FunctionEnter2` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)

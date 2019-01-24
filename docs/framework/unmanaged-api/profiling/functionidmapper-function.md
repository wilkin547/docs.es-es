---
title: FunctionIDMapper (Función)
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d65d918147423396a18d2ea5c3edf7ff60c26a11
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556134"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper (Función)
Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a otro identificador que se usará en el [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), y [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) devoluciones de llamada para esa función. Además, `FunctionIDMapper` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `funcId`  
 [in] Identificador de la función que se va a reasignar.  
  
 `pbHookFunction`  
 [out] Un puntero a un valor que establece el generador de perfiles en `true` si desea recibir `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` devoluciones de llamada; de lo contrario, establece este valor en `false`.  
  
## <a name="return-value"></a>Valor devuelto  
 El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo. El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`. En caso contrario, un valor null devuelto producirá resultados imprevisibles, que posiblemente incluyan la detención del proceso.  
  
## <a name="remarks"></a>Comentarios  
 El `FunctionIDMapper` función es una devolución de llamada. Se implementa mediante el generador de perfiles para volver a asignar un identificador de función a algún otro identificador que es más útil para el generador de perfiles. El `FunctionIDMapper` devuelve el identificador alternativo que se usará para una función determinada. El motor de ejecución respeta, a continuación, la solicitud del generador de perfiles pasando este Id. alternativo, además del identificador de la función tradicional, vuelva al generador de perfiles en el `clientData` parámetro de la `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` enlaces para identificar la función para la que se llama el enlace.  
  
 Puede usar el [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) método para especificar la implementación de la `FunctionIDMapper` función. Puede llamar a la `ICorProfilerInfo::SetFunctionIDMapper` método solo una vez y se recomienda que realice en el [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.  
  
 De forma predeterminada, se supone que un generador de perfiles que establece la marca COR_PRF_MONITOR_ENTERLEAVE utilizando [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), y que establece enlaces mediante [SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debería recibir el `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` devoluciones de llamada para cada función. Sin embargo, pueden implementar los generadores de perfiles `FunctionIDMapper` para evitar selectivamente la recepción de estas devoluciones de llamada para ciertas funciones estableciendo `pbHookFunction` a `false`.  
  
 Los generadores de perfiles deben ser tolerantes a los casos donde varios subprocesos de una aplicación de perfiles están llamando al mismo tiempo el mismo método o función. En tales casos, el generador de perfiles puede recibir varios `FunctionIDMapper` las devoluciones de llamada para el mismo `FunctionID`. El generador de perfiles debe tener la seguridad devolver los mismos valores de esta devolución de llamada cuando se llama varias veces con el mismo `FunctionID`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [SetFunctionIDMapper (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)

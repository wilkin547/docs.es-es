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
ms.openlocfilehash: 23c6f0a29160b6e1dc194cf360c07374c565522b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440707"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper (Función)
Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)y [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) para esa función. `FunctionIDMapper` también permite al generador de perfiles indicar si desea recibir devoluciones de llamada para esa función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `funcId`  
 [in] Identificador de la función que se va a reasignar.  
  
 `pbHookFunction`  
 enuncia Puntero a un valor que el generador de perfiles establece en `true` si desea recibir devoluciones de llamada `FunctionEnter2`, `FunctionLeave2`y `FunctionTailcall2`; de lo contrario, establece este valor en `false`.  
  
## <a name="return-value"></a>Valor devuelto  
 El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo. El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`. De lo contrario, un valor devuelto null producirá resultados imprevisibles, incluso la detención del proceso.  
  
## <a name="remarks"></a>Comentarios  
 La función `FunctionIDMapper` es una devolución de llamada. Lo implementa el generador de perfiles para reasignar un identificador de función a algún otro identificador que sea más útil para el generador de perfiles. El `FunctionIDMapper` devuelve el identificador alternativo que se va a utilizar para una función determinada. A continuación, el motor de ejecución respeta la solicitud del generador de perfiles pasando este ID. alternativo, además del identificador de función tradicional, de nuevo al generador de perfiles en el `clientData` parámetro de los enlaces `FunctionEnter2`, `FunctionLeave2`y `FunctionTailcall2` para identificar la función para la que se llama al enlace.  
  
 Puede usar el método [ICorProfilerInfo:: setfunctionidmapper (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) para especificar la implementación de la función `FunctionIDMapper`. Solo se puede llamar una vez al método `ICorProfilerInfo::SetFunctionIDMapper` y se recomienda hacerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) .  
  
 De forma predeterminada, se supone que un generador de perfiles que establece la marca COR_PRF_MONITOR_ENTERLEAVE mediante [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)y que establece enlaces a través de [ICorProfilerInfo:: SetEnterLeaveFunctionHooks (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debe recibir las devoluciones de llamada `FunctionEnter2`, `FunctionLeave2`y `FunctionTailcall2` para cada función. Sin embargo, los perfiles pueden implementar `FunctionIDMapper` para evitar de forma selectiva la recepción de estas devoluciones de llamada para ciertas funciones estableciendo `pbHookFunction` en `false`.  
  
 Los perfiles deben ser tolerantes a los casos en los que varios subprocesos de una aplicación de la que se va a crear el perfiles llamen al mismo método o función simultáneamente. En tales casos, el generador de perfiles puede recibir varias devoluciones de llamada de `FunctionIDMapper` para la misma `FunctionID`. Debe asegurarse de que el generador de perfiles devuelve los mismos valores de esta devolución de llamada cuando se llama varias veces con el mismo `FunctionID`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [SetFunctionIDMapper (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [FunctionEnter2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)

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
ms.openlocfilehash: d5bf6626e2c6ba15fa9a5da08bcf2d9052866750
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866949"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper (Función)
Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)y [FunctionTailcall2](functiontailcall2-function.md) para esa función. Además, `FunctionIDMapper` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parameters

- `funcId`

  \[en] el identificador de función que se va a reasignar.

- `pbHookFunction`

  \[out] puntero a un valor que el generador de perfiles establece en `true` si desea recibir devoluciones de llamada de `FunctionEnter2`, `FunctionLeave2`y `FunctionTailcall2`. de lo contrario, establece este valor en `false`.

## <a name="return-value"></a>Valor devuelto  
 El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo. El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`. De lo contrario, un valor devuelto null producirá resultados imprevisibles, incluso la detención del proceso.  
  
## <a name="remarks"></a>Notas  
 La función `FunctionIDMapper` es una devolución de llamada. Lo implementa el generador de perfiles para reasignar un identificador de función a algún otro identificador que sea más útil para el generador de perfiles. El `FunctionIDMapper` devuelve el identificador alternativo que se va a utilizar para una función determinada. A continuación, el motor de ejecución respeta la solicitud del generador de perfiles pasando este ID. alternativo, además del identificador de función tradicional, de nuevo al generador de perfiles en el `clientData` parámetro de los enlaces `FunctionEnter2`, `FunctionLeave2`y `FunctionTailcall2` para identificar la función para la que se llama al enlace.  
  
 Puede usar el método [ICorProfilerInfo:: setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md) para especificar la implementación de la función `FunctionIDMapper`. Solo se puede llamar una vez al método `ICorProfilerInfo::SetFunctionIDMapper` y se recomienda hacerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .  
  
 De forma predeterminada, se supone que un generador de perfiles que establece la marca COR_PRF_MONITOR_ENTERLEAVE mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)y que establece enlaces a través de [ICorProfilerInfo:: SetEnterLeaveFunctionHooks (](icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debe recibir las devoluciones de llamada `FunctionEnter2`, `FunctionLeave2`y `FunctionTailcall2` para cada función. Sin embargo, los perfiles pueden implementar `FunctionIDMapper` para evitar de forma selectiva la recepción de estas devoluciones de llamada para ciertas funciones estableciendo `pbHookFunction` en `false`.  
  
 Los perfiles deben ser tolerantes a los casos en los que varios subprocesos de una aplicación de la que se va a crear el perfiles llamen al mismo método o función simultáneamente. En tales casos, el generador de perfiles puede recibir varias devoluciones de llamada de `FunctionIDMapper` para la misma `FunctionID`. Debe asegurarse de que el generador de perfiles devuelve los mismos valores de esta devolución de llamada cuando se llama varias veces con el mismo `FunctionID`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [SetFunctionIDMapper (método)](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 (Función)](functionidmapper2-function.md)
- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionLeave2 (Función)](functionleave2-function.md)
- [FunctionTailcall2 (Función)](functiontailcall2-function.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)

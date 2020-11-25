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
ms.openlocfilehash: 17396d3038578c16b74c3717174dc0fa4dc17631
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722848"
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
  
## <a name="parameters"></a>Parámetros

- `funcId`

  \[en] el identificador de función que se va a reasignar.

- `pbHookFunction`

  \[out] un puntero a un valor que el generador de perfiles establece en `true` si desea recibir `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` devoluciones de llamada, y; de lo contrario, establece este valor en `false` .

## <a name="return-value"></a>Valor devuelto  

 El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo. El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`. De lo contrario, un valor devuelto null producirá resultados imprevisibles, incluso la detención del proceso.  
  
## <a name="remarks"></a>Comentarios  

 La `FunctionIDMapper` función es una devolución de llamada. Lo implementa el generador de perfiles para reasignar un identificador de función a algún otro identificador que sea más útil para el generador de perfiles. `FunctionIDMapper`Devuelve el identificador alternativo que se va a utilizar para una función determinada. A continuación, el motor de ejecución respeta la solicitud del generador de perfiles pasando este identificador alternativo, además del identificador de función tradicional, de nuevo al generador de perfiles en el `clientData` parámetro de los `FunctionEnter2` `FunctionLeave2` enlaces, y `FunctionTailcall2` , para identificar la función para la que se llama al enlace.  
  
 Puede usar el método [ICorProfilerInfo:: setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md) para especificar la implementación de la `FunctionIDMapper` función. Puede llamar al `ICorProfilerInfo::SetFunctionIDMapper` método solo una vez y se recomienda hacerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .  
  
 De forma predeterminada, se supone que un generador de perfiles que establece la marca COR_PRF_MONITOR_ENTERLEAVE mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)y que establece enlaces a través de [ICorProfilerInfo:: SetEnterLeaveFunctionHooks (](icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debe recibir las `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` devoluciones de llamada, y para cada función. Sin embargo, los profileres pueden implementar `FunctionIDMapper` para evitar de forma selectiva la recepción de estas devoluciones de llamada para ciertas funciones estableciendo `pbHookFunction` en `false` .  
  
 Los perfiles deben ser tolerantes a los casos en los que varios subprocesos de una aplicación de la que se va a crear el perfiles llamen al mismo método o función simultáneamente. En tales casos, el generador de perfiles puede recibir varias `FunctionIDMapper` devoluciones de llamada para el mismo `FunctionID` . El generador de perfiles debe asegurarse de que devuelve los mismos valores de esta devolución de llamada cuando se llama varias veces con el mismo `FunctionID` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 (Función)](functionidmapper2-function.md)
- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionLeave2 (Función)](functionleave2-function.md)
- [FunctionTailcall2 (Función)](functiontailcall2-function.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)

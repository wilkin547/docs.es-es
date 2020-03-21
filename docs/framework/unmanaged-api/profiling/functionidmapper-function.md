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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175179"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper (Función)
Notifica al generador de perfiles que el identificador especificado de una función se puede volver a asignar a un identificador alternativo que se usará en las devoluciones de llamada [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)y [FunctionTailcall2](functiontailcall2-function.md) para esa función. Además, `FunctionIDMapper` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Parámetros

- `funcId`

  \[en] El identificador de función que se va a reasignar.

- `pbHookFunction`

  \[out] Un puntero a un valor `true` que el generador `FunctionEnter2` `FunctionLeave2`de `FunctionTailcall2` perfiles establece si desea recibir , , y devoluciones de llamada; de lo contrario, `false`establece este valor en .

## <a name="return-value"></a>Valor devuelto  
 El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo. El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`. De lo contrario, un valor devuelto nulo producirá resultados impredecibles, incluida la posible detención del proceso.  
  
## <a name="remarks"></a>Observaciones  
 La `FunctionIDMapper` función es una devolución de llamada. El generador de perfiles lo implementa para reasignar un identificador de función a algún otro identificador que sea más útil para el generador de perfiles. El `FunctionIDMapper` devuelve el identificador alternativo que se usará para cualquier función dada. A continuación, el motor de ejecución respeta la solicitud del generador de perfiles pasando este identificador `clientData` alternativo, `FunctionEnter2` `FunctionLeave2`además del identificador de función tradicional, al generador de perfiles en el parámetro de , , y `FunctionTailcall2` los ganchos, para identificar la función para la que se llama al enlace.  
  
 Puede utilizar el método [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) para `FunctionIDMapper` especificar la implementación de la función. Puede llamar `ICorProfilerInfo::SetFunctionIDMapper` al método solo una vez y se recomienda que lo haga en la devolución de llamada [ICorProfilerCallback::Initialize.](icorprofilercallback-initialize-method.md)  
  
 De forma predeterminada, se supone que un generador de perfiles que establece la COR_PRF_MONITOR_ENTERLEAVE marca mediante [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md)y que establece los enlaces a través de [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debe recibir el `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` las devoluciones de llamada para cada función. Sin embargo, los `FunctionIDMapper` generadores de perfiles pueden implementar `pbHookFunction` para `false`evitar selectivamente recibir estas devoluciones de llamada para ciertas funciones estableciendo en .  
  
 Los generadores de perfiles deben ser tolerantes a los casos en los que varios subprocesos de una aplicación con perfiles llaman al mismo método o función simultáneamente. En tales casos, el generador `FunctionIDMapper` de perfiles `FunctionID`puede recibir varias devoluciones de llamada para el mismo archivo . El generador de perfiles debe estar seguro de devolver los mismos `FunctionID`valores de esta devolución de llamada cuando se llama varias veces con el mismo archivo .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 (Función)](functionidmapper2-function.md)
- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionLeave2 (Función)](functionleave2-function.md)
- [FunctionTailcall2 (Función)](functiontailcall2-function.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)

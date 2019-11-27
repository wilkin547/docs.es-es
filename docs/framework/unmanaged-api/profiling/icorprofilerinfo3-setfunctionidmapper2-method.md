---
title: ICorProfilerInfo3::SetFunctionIDMapper2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 2c06b9b7933245dc0e69e430a3fe4a515f8a50f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449578"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a>ICorProfilerInfo3::SetFunctionIDMapper2 (Método)
Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles. Este método extiende el método [ICorProfilerInfo:: setfunctionidmapper (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) con un parámetro de datos adicional, que los perfiles pueden utilizar para eliminar la ambigüedad entre los tiempos de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pFunc`  
 de Puntero a una implementación de [functionidmapper2 (](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) a la que se llamará para asignar los valores de `FunctionID` a sus valores alternativos.  
  
 `clientData`  
 de Puntero que se pasa a cada llamada de función [functionidmapper2 (](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) realizada por el tiempo de ejecución actual. El generador de perfiles puede utilizar esta información para eliminar la ambigüedad entre los tiempos de ejecución.  
  
## <a name="return-value"></a>Valor devuelto  
  
## <a name="remarks"></a>Comentarios  
 Las alternativas para los valores de FunctionID se pasarán a los enlaces de entrada y salida de función del generador de perfiles ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); o [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) especificados por el método [SetEnterLeaveFunctionHooks3 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) o [SetEnterLeaveFunctionHooks3WithInfo (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) .  
  
 El método `FunctionIDMapper2` solo se puede establecer una vez; se recomienda establecerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Setfunctionidmapper (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)

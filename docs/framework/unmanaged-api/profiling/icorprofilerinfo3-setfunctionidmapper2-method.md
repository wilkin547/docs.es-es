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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d04c15fa181d0e7bf8a92c1b6ecdef5b8b13bd7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182434"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a>ICorProfilerInfo3::SetFunctionIDMapper2 (Método)
Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles. Este método extiende la [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) método con un parámetro de datos adicionales, que pueden usar los generadores de perfiles para eliminar la ambigüedad entre los Runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pFunc`  
 [in] Un puntero a un [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementación que se llamará para asignar el `FunctionID` valores a sus valores alternativos.  
  
 `clientData`  
 [in] Un puntero que se pasa a cada [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) función llamada realizada por el tiempo de ejecución actual. El generador de perfiles puede utilizar esta información para eliminar la ambigüedad entre los Runtime.  
  
## <a name="return-value"></a>Valor devuelto  
  
## <a name="remarks"></a>Comentarios  
 Las alternativas para los valores de FunctionID se pasarán a enlaces de entrada y salida de función del generador de perfiles ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) ; o [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) que se especifican mediante el [ SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) o [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) método.  
  
 El `FunctionIDMapper2` método se puede establecer una sola vez; se recomienda establecerlo el [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3 (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)

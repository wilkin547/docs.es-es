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
ms.openlocfilehash: 26c26cf204f1a2743f46cfcfdfadbf2c3e3df38e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721574"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a>ICorProfilerInfo3::SetFunctionIDMapper2 (Método)

Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles. Este método extiende el método [ICorProfilerInfo:: setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md) con un parámetro de datos adicional, que los perfiles pueden utilizar para eliminar la ambigüedad entre los tiempos de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pFunc`  
 de Puntero a una implementación de [functionidmapper2 (](functionidmapper2-function.md) a la que se llamará para asignar los `FunctionID` valores a sus valores alternativos.  
  
 `clientData`  
 de Puntero que se pasa a cada llamada de función [functionidmapper2 (](functionidmapper2-function.md) realizada por el tiempo de ejecución actual. El generador de perfiles puede utilizar esta información para eliminar la ambigüedad entre los tiempos de ejecución.  
  
## <a name="return-value"></a>Valor devuelto  
  
## <a name="remarks"></a>Comentarios  

 Las alternativas para los valores de FunctionID se pasarán a los enlaces de entrada y salida de función del generador de perfiles ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md); o [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) especificados por el método [SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) o [SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) .  
  
 El `FunctionIDMapper2` método solo se puede establecer una vez; se recomienda establecerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

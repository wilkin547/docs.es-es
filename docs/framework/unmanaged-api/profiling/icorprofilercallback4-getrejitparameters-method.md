---
title: ICorProfilerCallback4::GetReJITParameters (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: 2cee763674da7472ca48355e7eaba3b7dfb7adbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730310"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>ICorProfilerCallback4::GetReJITParameters (Método)

Permite que el generador de perfiles de código establezca marcas de generación de código alternativas para un nuevo cuerpo de método recompilado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleID`  
 de Módulo que contiene el método para el que CLR necesita parámetros de recompilación JIT.  
  
 `methodId`  
 de `MethodDef` Del método para el que CLR necesita parámetros de recompilación JIT.  
  
 `pFunctionControl`  
 de Puntero a una interfaz [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) que el generador de perfiles puede usar para proporcionar información de recompilación JIT para el método que se va a volver a compilar.  
  
## <a name="remarks"></a>Comentarios  

 CLR emite una `GetReJITParameters` devolución de llamada para que el generador de perfiles pueda especificar los parámetros para volver a compilar un método determinado. La `GetReJITParameters` devolución de llamada se emite solo una vez por función; los parámetros proporcionados por el generador de perfiles se aplican a todas las instancias de esa función.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 (Interfaz)](icorprofilercallback4-interface.md)
- [Método JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
- [Método ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)

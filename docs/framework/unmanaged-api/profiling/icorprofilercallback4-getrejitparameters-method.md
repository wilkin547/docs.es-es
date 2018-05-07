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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f628bd1270b529264c14236ca7cdc03bf7afd9d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>ICorProfilerCallback4::GetReJITParameters (Método)
Permite que el generador de perfiles de código establecer las marcas de generación de código alternativo para un nuevo cuerpo de método ha vuelto a compilar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleID`  
 [in] El módulo que contiene el método para que el CLR debe parámetros de recompilación JIT.  
  
 `methodId`  
 [in] El `MethodDef` del método para que el CLR debe parámetros de recompilación JIT.  
  
 `pFunctionControl`  
 [in] Un puntero a un [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interfaz que puede usar el generador de perfiles para proporcionar información de recompilación JIT para el método que se va a volver a compilar.  
  
## <a name="remarks"></a>Comentarios  
 Los problemas CLR un `GetReJITParameters` devolución de llamada para que el generador de perfiles puede especificar los parámetros para volver a compilar un método determinado. El `GetReJITParameters` devolución de llamada se emite una sola vez por cada función; los parámetros proporcionados por el generador de perfiles se aplican a todas las instancias de esa función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [ReJITCompilationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)

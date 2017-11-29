---
title: "ICorProfilerFunctionControl::SetCodegenFlags (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetCodegenFlags
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eb212b0fb777e960d7121dadaf4715b44306db6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags (Método)
Establece una o más marcas de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración para controlar la generación de código de un just-in-time (JIT) vuelva a compilar la función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `flags`  
 [in] Una o más marcas de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración.  
  
## <a name="remarks"></a>Comentarios  
 El generador de perfiles Obtiene una instancia de esta interfaz mediante la [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) devolución de llamada. `SetCodegenFlags`permite que el generador de perfiles controlar la generación de código para la función ha vuelto a compilar. Al igual que con todos los demás parámetros de recompilación JIT, las marcas de generación de código se aplican a todas las instancias de la función.  
  
 El compilador JIT tiene en cuenta estas marcas de compilación, junto con otros indicadores especificados por otros orígenes, cuando se compila una función.  Los otros orígenes son el depurador, indicadores globales establecen por el generador de perfiles en el inicio, en el [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) (método) (con los valores `COR_PRF_DISABLE_INLINING` y `COR_PRF_DISABLE_OPTIMIZATIONS`) y el generador de perfiles [ ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) devolución de llamada.  El compilador JIT da prioridad a un origen que solicita la menor cantidad de optimización.  Por ejemplo, si especifica el generador de perfiles `COR_PRF_DISABLE_INLINING` durante el inicio, pero no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en el [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) devolución de llamada, la inclusión todavía está deshabilitado.  De forma similar, si no especifica el generador de perfiles `COR_PRF_CODEGEN_DISABLE_INLINING` en `SetCodegenFlags`, pero, a continuación, deshabilita la inclusión mediante el uso de la [ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) devolución de llamada, la inclusión está deshabilitado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerFunctionControl (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)

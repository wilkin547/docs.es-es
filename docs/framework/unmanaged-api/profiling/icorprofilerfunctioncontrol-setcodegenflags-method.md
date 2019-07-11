---
title: ICorProfilerFunctionControl::SetCodegenFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4103925462732fa8ddc509a9538ef5b485266a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780369"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags (Método)
Establece una o más marcas de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración a la generación de código de control para un just-in-time (JIT) vuelve a compilar la función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>Parámetros  
 `flags`  
 [in] Uno o más marcadores de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración.  
  
## <a name="remarks"></a>Comentarios  
 El generador de perfiles Obtiene una instancia de esta interfaz a través de la [Icorprofilercallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) devolución de llamada. `SetCodegenFlags` permite que el generador de perfiles controlar la generación de código para la función ha vuelto a compilar. Al igual que con todos los demás parámetros de recompilación JIT, las marcas de generación de código se aplican a todas las instancias de la función.  
  
 El compilador JIT tiene en cuenta estos marcadores de compilación, junto con otras marcas especificadas por otros orígenes, al compilar una función.  Los demás orígenes incluyen el depurador, indicadores globales establecen en el inicio mediante el generador de perfiles mediante el [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método (con los valores `COR_PRF_DISABLE_INLINING` y `COR_PRF_DISABLE_OPTIMIZATIONS`) y el generador de perfiles [ JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) devolución de llamada.  El compilador JIT da prioridad a un origen que solicita la menor cantidad de optimización.  Por ejemplo, si especifica el generador de perfiles `COR_PRF_DISABLE_INLINING` durante el inicio, pero no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en el [Icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) todavía está deshabilitada la devolución de llamada, inclusión entre líneas.  De forma similar, si no especifica el generador de perfiles `COR_PRF_CODEGEN_DISABLE_INLINING` en `SetCodegenFlags`, pero, a continuación, deshabilita la inserción mediante el uso de la [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) está deshabilitada la devolución de llamada, inclusión entre líneas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerFunctionControl (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)

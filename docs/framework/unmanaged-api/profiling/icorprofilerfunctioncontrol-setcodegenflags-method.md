---
title: ICorProfilerFunctionControl::SetCodegenFlags (método)
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
ms.openlocfilehash: 88c9f552b73af69ea4e1f64b75ed74ea762dcdfb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429943"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a>ICorProfilerFunctionControl::SetCodegenFlags (método)
Establece una o varias marcas de la enumeración [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) para controlar la generación de código para una función recompilada Just-in-Time (JIT).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a>Parámetros  
 `flags`  
 de Una o varias marcas de la enumeración [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) .  
  
## <a name="remarks"></a>Comentarios  
 El generador de perfiles obtiene una instancia de esta interfaz a través de la devolución de llamada [ICorProfilerCallback4:: getrejitparameters (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) . `SetCodegenFlags` permite al generador de perfiles controlar la generación de código para la función recompilada. Como con todos los demás parámetros de recompilación JIT, las marcas de generación de código se aplican a todas las instancias de la función.  
  
 El compilador JIT tiene en cuenta estas marcas de compilación, junto con otras marcas especificadas por otros orígenes, al compilar una función.  Los demás orígenes incluyen el depurador, las marcas globales establecidas por el generador de perfiles al iniciarse mediante el método [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) (con los valores `COR_PRF_DISABLE_INLINING` y `COR_PRF_DISABLE_OPTIMIZATIONS`) y la devolución de llamada [ICorProfilerCallback:: jitinlining (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) del generador de perfiles.  El compilador JIT da prioridad a un origen que solicita la menor cantidad de optimización.  Por ejemplo, si el generador de perfiles especifica `COR_PRF_DISABLE_INLINING` en el inicio, pero no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en la devolución de llamada [ICorProfilerFunctionControl:: setcodegenflags (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) , la inserción está todavía deshabilitada.  Del mismo modo, si el generador de perfiles no especifica `COR_PRF_CODEGEN_DISABLE_INLINING` en `SetCodegenFlags`, pero deshabilita la inserción mediante la devolución de llamada [ICorProfilerCallback:: jitinlining (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) , la inserción se deshabilita.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerFunctionControl (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)

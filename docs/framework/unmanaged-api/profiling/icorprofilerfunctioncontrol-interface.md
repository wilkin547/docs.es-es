---
title: ICorProfilerFunctionControl (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 733a8f0bc7e8c19823827297a50f9c6906614ca7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698395"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl (Interfaz)

Proporciona métodos que permiten a un generador de perfiles de código comunicarse con Common Language Runtime (CLR) para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md)|Establece una o varias marcas de la enumeración [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) para controlar la generación de código para una función recompilada Just-in-Time (JIT).|  
|[SetILFunctionBody (Método)](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.|  
|[SetILInstrumentedCodeMap (Método)](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|Establece un mapa de código para la función especificada usando las entradas del mapa de Common Intermediate Language (CIL) especificadas.|  
  
## <a name="remarks"></a>Comentarios  

 La interfaz `ICorProfilerFunctionControl` proporciona métodos para controlar la generación de código para una única función que se ha vuelto a compilar. El generador de perfiles obtiene una instancia de esta interfaz a través de la devolución de llamada [ICorProfilerCallback4:: getrejitparameters (](icorprofilercallback4-getrejitparameters-method.md) . Cada instancia de `ICorProfilerFunctionControl` controla todas las instancias de una función.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo4 (Interfaz)](icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Método EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)

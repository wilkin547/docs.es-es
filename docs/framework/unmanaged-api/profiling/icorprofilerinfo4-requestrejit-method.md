---
description: 'Más información sobre: ICorProfilerInfo4:: Requestrejit ((método)'
title: ICorProfilerInfo4::RequestReJIT (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
ms.openlocfilehash: 2da65c2db5722f689f1a8588169ea099aff71be6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799023"
---
# <a name="icorprofilerinfo4requestrejit-method"></a>ICorProfilerInfo4::RequestReJIT (Método)

Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cFunctions`  
 [in] Número de funciones que se va a recompilar.  
  
 `moduleIds`  
 [in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.  
  
 `methodIds`  
 [in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|Se intentó marcar todos los métodos para la recompilación con JIT. El generador de perfiles debe implementar el método [ICorProfilerCallback4:: rejiterror (](icorprofilercallback4-rejiterror-method.md) para determinar qué métodos se marcaron correctamente para la recompilación JIT.|  
|CORPROF_E_CALLBACK4_REQUIRED|El generador de perfiles debe implementar la interfaz [ICorProfilerCallback4](icorprofilercallback4-interface.md) para que se admita esta llamada.|  
|CORPROF_E_REJIT_NOT_ENABLED|No se habilitó la recompilación con JIT. Debe habilitar la recompilación JIT durante la inicialización mediante el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer la `COR_PRF_ENABLE_REJIT` marca.|  
|E_INVALIDARG|`cFunctions` es 0, o `moduleIds` o `methodIds` es `NULL`.|  
|||  
|E_OUTOFMEMORY|El CLR no pudo completar la solicitud porque se quedó sin memoria.|  
  
## <a name="remarks"></a>Observaciones  

 Llame a `RequestReJIT` para que el tiempo de ejecución recompile un conjunto especificado de funciones. Un generador de perfiles de código puede utilizar la interfaz [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) para ajustar el código que se genera cuando se vuelven a compilar las funciones. Esto no afecta a las funciones actualmente en ejecución, solo a futuras llamadas a funciones. Si alguna de las funciones especificadas ya se había recompilado con JIT, la solicitud de recompilación equivale a revertir y recompilar la función. Para conservar la reversibilidad, cuando el compilador JIT compila la versión original de una función, solo tiene en cuenta las versiones originales de los destinatarios para las decisiones de inserción. Cuando el compilador JIT recompila una función, tiene en cuenta las versiones actuales (recompiladas u originales) de los destinatarios para la inserción.  
  
 Normalmente, un generador de perfiles llama a `RequestReJIT` en respuesta a una entrada del usuario que solicita que el generador de perfiles instrumente uno o más métodos. Normalmente, `RequestReJIT` suspende el tiempo de ejecución para realizar algunas de sus tareas y puede desencadenar una recolección de elementos no utilizados. Por lo tanto, el generador de perfiles debe llamar a `RequestReJIT` desde un subproceso creado anteriormente y no desde un subproceso creado por el CLR que está ejecutando actualmente una devolución de llamada del generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo4 (Interfaz)](icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)

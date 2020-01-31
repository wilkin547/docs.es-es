---
title: ICorProfilerCallback::JITCompilationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: f1cfef464569b577923fbb16624c99358998d29c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866252"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>ICorProfilerCallback::JITCompilationFinished (Método)
Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameters

- `functionId`

  \[en] identificador de la función que se compiló.

- `hrStatus`

  \[en] un valor que indica si la compilación se realizó correctamente.

- `fIsSafeToBlock`

  \[in] un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución. El valor es `true` si el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; de lo contrario, `false`.

  Aunque el valor `true` no perjudicará el tiempo de ejecución, puede sesgar los resultados de la generación de perfiles.

## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [JITCompilationStarted (método)](icorprofilercallback-jitcompilationstarted-method.md)

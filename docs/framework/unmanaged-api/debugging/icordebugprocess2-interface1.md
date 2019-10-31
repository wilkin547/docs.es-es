---
title: ICorDebugProcess2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
ms.openlocfilehash: 213eb86c36225a6194af83c04c469fbe0cc51b63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137149"
---
# <a name="icordebugprocess2-interface"></a>ICorDebugProcess2 (Interfaz)
Extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|Quita un punto de interrupción en el desplazamiento especificado establecido por una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint`.|  
|[GetDesiredNGENCompilerFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|Obtiene las marcas que se deben establecer para el Common Language Runtime (CLR) para cargar la imagen en el proceso al que hace referencia esta `ICorDebugProcess2`.|  
|[GetReferenceValueFromGCHandle (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.|  
|[GetThreadForTaskID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|Obtiene el subproceso en el que se está ejecutando la tarea con el identificador especificado.|  
|[GetVersion (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|Obtiene la versión de CLR en la que se está ejecutando el proceso que se está depurando.|  
|[SetDesiredNGENCompilerFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|Establece las marcas necesarias para que el compilador Just-in-Time (JIT) cargue una imagen en el proceso que se está depurando.|  
|[SetUnmanagedBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: Interfaz ICorDebugProcess2
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
ms.openlocfilehash: 1ef6af11851acbe0f7e9469c9432ff09f9228608
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792507"
---
# <a name="icordebugprocess2-interface"></a>Interfaz ICorDebugProcess2
Extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ClearUnmanagedBreakpoint (método)](icordebugprocess2-clearunmanagedbreakpoint-method.md)|Quita un punto de interrupción en el desplazamiento especificado establecido por una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint`.|  
|[GetDesiredNGENCompilerFlags (método)](icordebugprocess2-getdesiredngencompilerflags-method.md)|Obtiene las marcas que se deben establecer para el Common Language Runtime (CLR) para cargar la imagen en el proceso al que hace referencia esta `ICorDebugProcess2`.|  
|[GetReferenceValueFromGCHandle (método)](icordebugprocess2-getreferencevaluefromgchandle-method.md)|Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.|  
|[GetThreadForTaskID (método)](icordebugprocess2-getthreadfortaskid-method.md)|Obtiene el subproceso en el que se está ejecutando la tarea con el identificador especificado.|  
|[GetVersion (método)](icordebugprocess2-getversion-method.md)|Obtiene la versión de CLR en la que se está ejecutando el proceso que se está depurando.|  
|[SetDesiredNGENCompilerFlags (método)](icordebugprocess2-setdesiredngencompilerflags-method.md)|Establece las marcas necesarias para que el compilador Just-in-Time (JIT) cargue una imagen en el proceso que se está depurando.|  
|[SetUnmanagedBreakpoint (método)](icordebugprocess2-setunmanagedbreakpoint-method.md)|Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)

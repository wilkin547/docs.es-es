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
ms.openlocfilehash: 1a57b7ceb6da961fba1f0d6e8e0ba1aa88ca0541
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213496"
---
# <a name="icordebugprocess2-interface"></a>Interfaz ICorDebugProcess2
Extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md)|Quita un punto de interrupción en el desplazamiento especificado establecido por una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint` .|  
|[Método GetDesiredNGENCompilerFlags](icordebugprocess2-getdesiredngencompilerflags-method.md)|Obtiene las marcas que se deben establecer para el Common Language Runtime (CLR) para cargar la imagen en el proceso al que hace referencia `ICorDebugProcess2` .|  
|[Método GetReferenceValueFromGCHandle](icordebugprocess2-getreferencevaluefromgchandle-method.md)|Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.|  
|[Método GetThreadForTaskID](icordebugprocess2-getthreadfortaskid-method.md)|Obtiene el subproceso en el que se está ejecutando la tarea con el identificador especificado.|  
|[Método GetVersion](icordebugprocess2-getversion-method.md)|Obtiene la versión de CLR en la que se está ejecutando el proceso que se está depurando.|  
|[Método SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md)|Establece las marcas necesarias para que el compilador Just-in-Time (JIT) cargue una imagen en el proceso que se está depurando.|  
|[Método SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)|Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)

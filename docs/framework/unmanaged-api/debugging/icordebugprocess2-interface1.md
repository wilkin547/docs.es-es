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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b3bb51f307093ea1cc8cc45064d5c405974822
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178027"
---
# <a name="icordebugprocess2-interface"></a>Interfaz ICorDebugProcess2
Una extensión lógica de la interfaz ICorDebugProcess, que representa un proceso que ejecuta código administrado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|Quita un punto de interrupción en el desplazamiento especificado que se ha establecido mediante una llamada anterior a `ICorDebugProcess2::SetUnmanagedBreakpoint`.|  
|[Método GetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|Obtiene las marcas que se deben establecer para common language runtime (CLR) para cargar la imagen en el proceso que hace referencia esta `ICorDebugProcess2`.|  
|[Método GetReferenceValueFromGCHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|Obtiene un puntero de referencia al objeto administrado especificado que tiene una colección de elementos no utilizados de identificador.|  
|[Método GetThreadForTaskID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|Obtiene el subproceso en el que se ejecuta la tarea con el identificador especificado.|  
|[Método GetVersion](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|Obtiene la versión de CLR en el que se está ejecutando el proceso que se está depurando.|  
|[Método SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|Establece las marcas que son necesarias para el compilador de just-in-time (JIT) cargar una imagen en el proceso que se está depurando.|  
|[Método SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|Establece un punto de interrupción no administrado en el desplazamiento de la imagen nativa especificada.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

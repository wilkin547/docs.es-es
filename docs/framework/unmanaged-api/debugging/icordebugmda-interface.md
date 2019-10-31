---
title: ICorDebugMDA (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: 4201fe23bf54388510088e21471edce91809e94c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129801"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA (Interfaz)
Representa un mensaje del asistente para la depuración administrada (MDA).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetDescription (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Obtiene una cadena que contiene una descripción de este MDA.|  
|[GetFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Obtiene las marcas asociadas a este MDA.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Obtiene una cadena que contiene el nombre de este MDA.|  
|[GetOSThreadId (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Obtiene el identificador del subproceso del sistema operativo en el que se ejecuta este MDA.|  
|[GetXML (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Obtiene la secuencia XML completa asociada a este MDA.|  
  
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
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

---
title: LoggingLevelEnum (Enumeración)
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe8e1355382273a681e927897f4a8ff5814b8de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765432"
---
# <a name="logginglevelenum-enumeration"></a>LoggingLevelEnum (Enumeración)
Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`LTraceLevel0`|El mensaje es un nivel de seguimiento 0.|  
|`LTraceLevel1`|El mensaje es un nivel de seguimiento 1.|  
|`LTraceLevel2`|El mensaje es un nivel de seguimiento 2.|  
|`LTraceLevel3`|El mensaje es un nivel de seguimiento 3.|  
|`LTraceLevel4`|El mensaje es un nivel de seguimiento 4.|  
|`LStatusLevel0`|El mensaje es un nivel de estado 0.|  
|`LStatusLevel1`|El mensaje es un nivel de estado 1.|  
|`LStatusLevel2`|El mensaje es un nivel de estado 2.|  
|`LStatusLevel3`|El mensaje es un nivel de estado 3.|  
|`LStatusLevel4`|El mensaje es un nivel de estado 4.|  
|`LWarningLevel`|El mensaje es un nivel de advertencia.|  
|`LErrorLevel`|El mensaje es un nivel de error.|  
|`LPanicLevel`|El mensaje es un nivel de pánico.|  
  
## <a name="remarks"></a>Comentarios  
 Common language runtime (CLR) llama a la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) método para notificar al depurador que un subproceso administrado ha iniciado sesión un evento. El CLR pasa un valor de la `LoggingLevelEnum` enumeración para indicar el nivel de gravedad del mensaje que el subproceso administrado se escribió en el registro de eventos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.EventLog>
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

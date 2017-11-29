---
title: "Enumeración CorDebugDebugEventKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDebugEventKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5aeb6085671e645e12713944d6456b9581a3886f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdebugeventkind-enumeration"></a>Enumeración CorDebugDebugEventKind
Indica el tipo de evento cuya información se descodifica por la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|Evento load del módulo.|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|Evento unload del módulo.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|Primera excepción.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|Primera excepción de usuario.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|Excepción para la que existe un controlador `catch`.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|Excepción sin controlar.|  
  
## <a name="remarks"></a>Comentarios  
 Un miembro de la `CorDebugDebugEventKind` enumeración devuelto por una llamada a la [icordebugdebugevent::](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) (método).  
  
> [!NOTE]
>  Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

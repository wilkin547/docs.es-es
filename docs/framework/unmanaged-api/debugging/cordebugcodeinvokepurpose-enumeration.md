---
title: Enumeración CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 858dfe9b15422680a261fef9e22d8c89d9d7fe45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155576"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>Enumeración CorDebugCodeInvokePurpose
Explica los motivos por los que una función exportada llama a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|Ninguno o desconocido.|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|El código administrado ejecutará cualquier punto de entrada administrado, como una PInvoke inversa. Cualquier otro propósito más detallado es desconocido para el tiempo de ejecución.|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|El código administrado ejecutará un constructor estático.|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|El código administrado ejecutará la implementación de un método de interfaz que se haya llamado.|  
  
## <a name="remarks"></a>Comentarios  
 Esta enumeración se utiliza en el [icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) método para proporcionar información sobre la ejecución paso a paso el código administrado.  
  
> [!NOTE]
>  Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

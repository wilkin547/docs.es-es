---
title: "Enumeración CorDebugCodeInvokeKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCodeInvokeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d46a47c7c655a960224bb836be0ea37cd07c8038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a>Enumeración CorDebugCodeInvokeKind
Describe cómo una función exportada invoca a código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|Si algún código administrado se invoca mediante este método, tendrá que encontrarse más adelante mediante eventos explícitos o puntos de interrupción.<br /><br /> O bien<br /><br /> Puede que falte parte del código administrado al que este método llama porque no hay forma fácil de detenerse en él.<br /><br /> O bien<br /><br /> El método no puede invocar nunca código administrado.|  
|`CODE_INVOKE_KIND_RETURN`|Este método llamará a código administrado mediante una instrucción de devolución. El paso a paso para salir debe llegar en el siguiente código administrado.|  
|`CODE_INVOKE_KIND_TAILCALL`|Este método invocará código administrado mediante una llamada de cola. El paso a paso y el paso a paso por procedimientos sobre instrucciones de llamada deben llegar en el código administrado.|  
  
## <a name="remarks"></a>Comentarios  
 Esta enumeración se usa en la [icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) método para proporcionar información acerca de la ejecución paso a paso el código administrado.  
  
> [!NOTE]
>  Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

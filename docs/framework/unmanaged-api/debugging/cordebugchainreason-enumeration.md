---
title: "CorDebugChainReason (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugChainReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugChainReason
helpviewer_keywords: CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1951983c9d167862169bd6178dc65693d724dc0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugchainreason-enumeration"></a>CorDebugChainReason (Enumeración)
Indica el motivo o los motivos para que se inicie una cadena de llamadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`CHAIN_NONE`|No se inició ninguna cadena de llamadas.|  
|`CHAIN_CLASS_INIT`|Un constructor inició la cadena.|  
|`CHAIN_EXCEPTION_FILTER`|Un constructor inició la cadena.|  
|`CHAIN_SECURITY`|El código que exige la seguridad inició la cadena.|  
|`CHAIN_CONTEXT_POLICY`|Una directiva de contexto inició la cadena.|  
|`CHAIN_INTERCEPTION`|No usado.|  
|`CHAIN_PROCESS_START`|No usado.|  
|`CHAIN_THREAD_START`|El inicio de la ejecución de un subproceso inició la cadena.|  
|`CHAIN_ENTER_MANAGED`|Una entrada en código administrado inició la cadena.|  
|`CHAIN_ENTER_UNMANAGED`|Una entrada en código no administrado inició la cadena.|  
|`CHAIN_DEBUGGER_EVAL`|No usado.|  
|`CHAIN_CONTEXT_SWITCH`|No usado.|  
|`CHAIN_FUNC_EVAL`|Una evaluación de función inició la cadena.|  
  
## <a name="remarks"></a>Comentarios  
 Use la [ICorDebugChain:: GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) método para determinar las razones para la iniciación de una cadena de llamadas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

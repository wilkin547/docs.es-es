---
title: ICorDebugFunction2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: da440b7d2da57511545d3b63700662eb544660fd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137777"
---
# <a name="icordebugfunction2-interface"></a>ICorDebugFunction2 (Interfaz)

Extiende lógicamente la interfaz ICorDebugFunction para proporcionar compatibilidad con Solo mi código depuración paso a paso, que omite el código que no es de usuario.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateNativeCode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|(Aún no implementado). Obtiene un puntero de interfaz a un ICorDebugCodeEnum (que contiene las instrucciones de código nativo en la función a la que hace referencia este objeto ICorDebugFunction2.|  
|[GetJMCStatus (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|Obtiene un valor que indica si esta función está marcada como código de usuario.|  
|[GetVersionNumber (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|Obtiene la versión de edición y continuación de esta función.|  
|[SetJMCStatus (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|Marca esta función para Solo mi código la ejecución paso a paso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

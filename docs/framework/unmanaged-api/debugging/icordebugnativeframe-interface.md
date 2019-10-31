---
title: ICorDebugNativeFrame (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 04bdbc49217236bc6c05a718cb4d42067cafd8bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096673"
---
# <a name="icordebugnativeframe-interface"></a>ICorDebugNativeFrame (Interfaz)

Implementación especializada de ICorDebugFrame utilizada para los marcos nativos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanSetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.|  
|[GetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Obtiene el desplazamiento del marco de pila en código nativo.|  
|[GetLocalDoubleRegisterValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Obtiene un puntero a un ICorDebugValue que representa el valor de un argumento o una variable local almacenados en dos registros de memoria de un marco nativo.|  
|[GetLocalMemoryRegisterValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Obtiene un puntero a una `ICorDebugValue` que representa el valor de una variable local, de la que los bits bajos se almacenan en el registro especificado y los bits altos se almacenan en la dirección de memoria especificada.|  
|[GetLocalMemoryValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.|  
|[GetLocalRegisterMemoryValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Obtiene un puntero a una `ICorDebugValue` que representa el valor de una variable local, cuyos bits altos se almacenan en el registro especificado y los bits bajos se almacenan en la dirección de memoria especificada.|  
|[GetLocalRegisterValue (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Obtiene un puntero a una `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.|  
|[GetRegisterSet (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Obtiene un puntero a un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) que representa el conjunto de registros para esta `ICorDebugNativeFrame`.|  
|[SetIP (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.|  
  
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

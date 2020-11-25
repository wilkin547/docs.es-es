---
title: Interfaz ICorDebugNativeFrame
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
ms.openlocfilehash: 043dc0fdd5218d7bc6b80428d1eb891b3f01ee8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695561"
---
# <a name="icordebugnativeframe-interface"></a>Interfaz ICorDebugNativeFrame

Implementación especializada de ICorDebugFrame utilizada para los marcos nativos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CanSetIP](icordebugnativeframe-cansetip-method.md)|Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.|  
|[Método GetIP](icordebugnativeframe-getip-method.md)|Obtiene el desplazamiento del marco de pila en código nativo.|  
|[Método GetLocalDoubleRegisterValue](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Obtiene un puntero a un ICorDebugValue que representa el valor de un argumento o una variable local almacenados en dos registros de memoria de un marco nativo.|  
|[Método GetLocalMemoryRegisterValue](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, cuyos bits bajos se almacenan en el registro especificado y los bits altos se almacenan en la dirección de memoria especificada.|  
|[Método GetLocalMemoryValue](icordebugnativeframe-getlocalmemoryvalue-method.md)|Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.|  
|[Método GetLocalRegisterMemoryValue](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local, cuyos bits altos se almacenan en el registro especificado y los bits bajos se almacenan en la dirección de memoria especificada.|  
|[Método GetLocalRegisterValue](icordebugnativeframe-getlocalregistervalue-method.md)|Obtiene un puntero a un `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.|  
|[GetRegisterSet (Método)](icordebugnativeframe-getregisterset-method.md)|Obtiene un puntero a un [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para este `ICorDebugNativeFrame` .|  
|[SetIP (Método)](icordebugnativeframe-setip-method.md)|Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)

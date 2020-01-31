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
ms.openlocfilehash: 41ac0b29ade2f78b893df72e8a17624373f6dd78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792785"
---
# <a name="icordebugnativeframe-interface"></a>Interfaz ICorDebugNativeFrame

Implementación especializada de ICorDebugFrame utilizada para los marcos nativos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CanSetIP (método)](icordebugnativeframe-cansetip-method.md)|Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.|  
|[GetIP (método)](icordebugnativeframe-getip-method.md)|Obtiene el desplazamiento del marco de pila en código nativo.|  
|[GetLocalDoubleRegisterValue (método)](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Obtiene un puntero a un ICorDebugValue que representa el valor de un argumento o una variable local almacenados en dos registros de memoria de un marco nativo.|  
|[GetLocalMemoryRegisterValue (método)](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Obtiene un puntero a una `ICorDebugValue` que representa el valor de una variable local, de la que los bits bajos se almacenan en el registro especificado y los bits altos se almacenan en la dirección de memoria especificada.|  
|[GetLocalMemoryValue (método)](icordebugnativeframe-getlocalmemoryvalue-method.md)|Obtiene un puntero a un `ICorDebugValue` que representa el valor de una variable local almacenada en la dirección de memoria especificada.|  
|[GetLocalRegisterMemoryValue (método)](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Obtiene un puntero a una `ICorDebugValue` que representa el valor de una variable local, cuyos bits altos se almacenan en el registro especificado y los bits bajos se almacenan en la dirección de memoria especificada.|  
|[GetLocalRegisterValue (método)](icordebugnativeframe-getlocalregistervalue-method.md)|Obtiene un puntero a una `ICorDebugValue` que representa el valor de un argumento o una variable local almacenada en el registro nativo especificado.|  
|[GetRegisterSet (método)](icordebugnativeframe-getregisterset-method.md)|Obtiene un puntero a un [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para esta `ICorDebugNativeFrame`.|  
|[SetIP (método)](icordebugnativeframe-setip-method.md)|Establece el puntero de instrucción en la ubicación de desplazamiento especificada en código nativo.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)

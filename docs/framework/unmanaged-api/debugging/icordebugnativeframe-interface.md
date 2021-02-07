---
description: 'Más información acerca de: ICorDebugNativeFrame (interfaz)'
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
ms.openlocfilehash: e417184c9f1ca5136e1b4dba07820fd8242ae932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729139"
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
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)

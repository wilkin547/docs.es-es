---
description: 'Más información acerca de: interfaz ICorDebugILFrame3'
title: ICorDebugILFrame3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: a34a3f0941871a2d0a63fb2d9f78ccb7ff455866
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791262"
---
# <a name="icordebugilframe3-interface"></a>ICorDebugILFrame3 (Interfaz)

Proporciona un método que encapsula el valor devuelto de una función. `ICorDebugILFrame3` es una extensión lógica de las interfaces ICorDebugILFrame e ICorDebugILFrame2.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)|Obtiene un objeto ICorDebugValue que encapsula el valor devuelto de una función.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugCode3 (Interfaz)](icordebugcode3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)

---
title: ICorDebugThread4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
ms.openlocfilehash: 5c108420772be9e6d0932f3759f18da9446f99d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727944"
---
# <a name="icordebugthread4-interface"></a>ICorDebugThread4 (Interfaz)

Proporciona información de bloqueo de subprocesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetBlockingObjects](icordebugthread4-getblockingobjects-method.md)|Proporciona una enumeración ordenada de las estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) que proporcionan información de bloqueo de subprocesos.|  
|[Método HadUnhandledException](icordebugthread4-hadunhandledexception-method.md)|Indica si el subproceso ha tenido alguna vez una excepción no controlada.|  
|[Método GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.|  
  
## <a name="remarks"></a>Comentarios  

 Esta interfaz es una extensión lógica de las interfaces ICorDebugThread, ICorDebugThread2 y [ICorDebugThread3](icordebugthread3-interface.md) .  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

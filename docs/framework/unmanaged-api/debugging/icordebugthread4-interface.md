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
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791334"
---
# <a name="icordebugthread4-interface"></a>ICorDebugThread4 (Interfaz)
Proporciona información de bloqueo de subprocesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetBlockingObjects (método)](icordebugthread4-getblockingobjects-method.md)|Proporciona una enumeración ordenada de las estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) que proporcionan información de bloqueo de subprocesos.|  
|[HadUnhandledException (método)](icordebugthread4-hadunhandledexception-method.md)|Indica si el subproceso ha tenido alguna vez una excepción no controlada.|  
|[GetCurrentCustomDebuggerNotification (método)](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.|  
  
## <a name="remarks"></a>Notas  
 Esta interfaz es una extensión lógica de las interfaces ICorDebugThread, ICorDebugThread2 y [ICorDebugThread3](icordebugthread3-interface.md) .  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)

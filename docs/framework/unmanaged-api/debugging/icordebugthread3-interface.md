---
title: ICorDebugThread3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 19bd869aec7e4d046890d2314f5142753ba0b112
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791389"
---
# <a name="icordebugthread3-interface"></a>ICorDebugThread3 (Interfaz)
Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateStackWalk (método)](icordebugthread3-createstackwalk-method.md)|Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.|  
|[GetActiveInternalFrames (método)](icordebugthread3-getactiveinternalframes-method.md)|Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.|  
  
## <a name="remarks"></a>Notas  
 `ICorDebugThread3` es una extensión lógica de la interfaz ICorDebugThread.  
  
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

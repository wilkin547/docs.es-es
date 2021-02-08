---
description: 'Más información acerca de: interfaz ICorDebugThread3'
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
ms.openlocfilehash: 88c668f1e08d0843f26d231937c85d80e03bee6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800973"
---
# <a name="icordebugthread3-interface"></a>ICorDebugThread3 (Interfaz)

Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateStackWalk](icordebugthread3-createstackwalk-method.md)|Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.|  
|[Método GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md)|Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.|  
  
## <a name="remarks"></a>Observaciones  

 `ICorDebugThread3` es una extensión lógica de la interfaz ICorDebugThread.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

---
title: ICorDebugInternalFrame2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: ce3ca4745727a1738fdc1a526480d70ffc55ccf8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209908"
---
# <a name="icordebuginternalframe2-interface"></a>ICorDebugInternalFrame2 (Interfaz)
Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición con respecto a los objetos ICorDebugFrame.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetFrameAddress](icordebuginternalframe2-getframeaddress-method.md)|Devuelve la dirección de la pila del marco interno.|  
|[Método IsCloserToLeaf](icordebuginternalframe2-isclosertoleaf-method.md)|Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.|  
  
## <a name="remarks"></a>Observaciones  
 Esta interfaz extiende la interfaz ICorDebugInternalFrame (.  
  
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

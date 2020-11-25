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
ms.openlocfilehash: a17c46d5ef08963bb0d7fc280ba8b90531e41c5b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719637"
---
# <a name="icordebuginternalframe2-interface"></a>ICorDebugInternalFrame2 (Interfaz)

Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición con respecto a los objetos ICorDebugFrame.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetFrameAddress](icordebuginternalframe2-getframeaddress-method.md)|Devuelve la dirección de la pila del marco interno.|  
|[Método IsCloserToLeaf](icordebuginternalframe2-isclosertoleaf-method.md)|Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.|  
  
## <a name="remarks"></a>Comentarios  

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

---
title: ICorDebugProcess3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
ms.openlocfilehash: 826736d2db7aa1e618a2e5fe0655cedad9556b17
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213444"
---
# <a name="icordebugprocess3-interface"></a>ICorDebugProcess3 (Interfaz)
Controla las notificaciones del depurador personalizadas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md)|Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.|  
  
## <a name="remarks"></a>Observaciones  
 Esta interfaz extiende lógicamente las interfaces ICorDebugProcess e ICorDebugProcess2.  
  
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

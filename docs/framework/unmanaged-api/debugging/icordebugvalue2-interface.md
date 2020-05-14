---
title: ICorDebugValue2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: d036ddf353aa3a622ade05e1e2daa7f170d28f63
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396778"
---
# <a name="icordebugvalue2-interface"></a>ICorDebugValue2 (Interfaz)
Extiende la interfaz "ICorDebugValue" para proporcionar compatibilidad con objetos "ICorDebugType".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetExactType](icordebugvalue2-getexacttype-method.md)|Obtiene un puntero de interfaz a un `ICorDebugType` objeto que representa el <xref:System.Type> de este valor.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)

- [ICorDebugValue3 (Interfaz)](icordebugvalue3-interface.md)

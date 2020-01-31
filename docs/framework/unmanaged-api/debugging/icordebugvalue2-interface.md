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
ms.openlocfilehash: c6f20b0f7927d79ee56b5b6962137d668dc048d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791118"
---
# <a name="icordebugvalue2-interface"></a>ICorDebugValue2 (Interfaz)
Extiende la interfaz "ICorDebugValue" para proporcionar compatibilidad con objetos "ICorDebugType".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetExactType (método)](icordebugvalue2-getexacttype-method.md)|Obtiene un puntero de interfaz a un objeto `ICorDebugType` que representa el <xref:System.Type> de este valor.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)

- [ICorDebugValue3 (interfaz)](icordebugvalue3-interface.md)

---
title: Interfaz ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695821"
---
# <a name="icordebugmoduledebugevent-interface"></a>Interfaz ICorDebugModuleDebugEvent

Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetModule (Método)](icordebugmoduledebugevent-getmodule-method.md)|Obtiene el módulo combinado que se acaba de cargar o descargar.|  
  
## <a name="remarks"></a>Comentarios  

 Los tipos de evento [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementan esta interfaz.  
  
> [!NOTE]
> La interfaz solo está disponible con .NET Native. Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

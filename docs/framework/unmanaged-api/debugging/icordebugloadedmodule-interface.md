---
title: Interfaz de ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 9fe36497844b9c33cefcf8c63711941196847525
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122616"
---
# <a name="icordebugloadedmodule-interface"></a>Interfaz de ICorDebugLoadedModule
Proporciona información acerca de un módulo cargado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetBaseAddress (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|Obtiene la dirección base del módulo cargado.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|Obtiene el nombre del módulo cargado.|  
|[GetSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|Obtiene el tamaño, en bytes, del módulo cargado.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz `ICorDebugLoadedModule` es implementada por un depurador y utiliza por interfaces de depuración de CLR para obtener información acerca del módulo cargado desde el depurador.  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

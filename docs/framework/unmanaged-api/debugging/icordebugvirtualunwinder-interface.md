---
title: Interfaz de ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb04ac42b3cc77db3af53c87efb0d1f1f75da928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvirtualunwinder-interface"></a>Interfaz de ICorDebugVirtualUnwinder
Proporciona métodos que ayudan al desenredo de la pila.  
  
## <a name="methods"></a>Métodos  
  
|Método|nombre|  
|------------|----------|  
|[GetContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|Obtiene el contexto actual de este responsable del desenredado.|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|Avanza hasta el contexto del llamador.|  
  
## <a name="remarks"></a>Comentarios  
 Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.  
  
> [!NOTE]
>  Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

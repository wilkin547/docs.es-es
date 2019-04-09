---
title: Interfaz de ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639cfc514d2a206f0de72db4b0bac02b53305ae3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083405"
---
# <a name="icordebugvirtualunwinder-interface"></a>Interfaz de ICorDebugVirtualUnwinder
Proporciona métodos que ayudan al desenredo de la pila.  
  
## <a name="methods"></a>Métodos  
  
|Método|Name|  
|------------|----------|  
|[Método GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|Obtiene el contexto actual de este responsable del desenredado.|  
|[Método Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|Avanza hasta el contexto del llamador.|  
  
## <a name="remarks"></a>Comentarios  
 Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.  
  
> [!NOTE]
>  Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

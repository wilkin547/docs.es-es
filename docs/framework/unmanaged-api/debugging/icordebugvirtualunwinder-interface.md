---
title: ICorDebugVirtualUnwinder (Interfaz)
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 065f71e45c2a56dbaa16a45f70958ca3dea80c48
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790825"
---
# <a name="icordebugvirtualunwinder-interface"></a>ICorDebugVirtualUnwinder (Interfaz)
Proporciona métodos que ayudan al desenredo de la pila.  
  
## <a name="methods"></a>Métodos  
  
|Método|Name|  
|------------|----------|  
|[GetContext (método)](icordebugvirtualunwinder-getcontext-method.md)|Obtiene el contexto actual de este responsable del desenredado.|  
|[Next (método)](icordebugvirtualunwinder-next-method.md)|Avanza hasta el contexto del llamador.|  
  
## <a name="remarks"></a>Notas  
 Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)

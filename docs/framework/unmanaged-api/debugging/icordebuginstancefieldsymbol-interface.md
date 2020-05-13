---
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 092f2a8acdffa9f91176bdf0ca10b8db9cff6d37
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209935"
---
# <a name="icordebuginstancefieldsymbol-interface"></a>Interfaz ICorDebugInstanceFieldSymbol
Representa la información de símbolos de depuración para un campo de instancia.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetName](icordebuginstancefieldsymbol-getname-method.md)|Obtiene el nombre del campo de instancia.|  
|[Método GetOffset](icordebuginstancefieldsymbol-getoffset-method.md)|Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.|  
|[Método GetSize](icordebuginstancefieldsymbol-getsize-method.md)|Obtiene el tamaño, en bytes, del campo de instancia.|  
  
## <a name="remarks"></a>Observaciones  
 La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

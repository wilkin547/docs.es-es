---
description: 'Más información acerca de: interfaz ICorDebugInstanceFieldSymbol'
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: aa47c858ec5b4b0d04b851357fe81c0fc9b2e30a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791138"
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
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

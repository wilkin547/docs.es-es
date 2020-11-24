---
title: Interfaz ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 3d808fd49eb7767f1f48ad4e07d8ba7e47c8f34b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679486"
---
# <a name="icordebugvariablesymbol-interface"></a>Interfaz ICorDebugVariableSymbol

Recupera la información de símbolos de depuración para una variable.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetName (Método)](icordebugvariablesymbol-getname-method.md)|Obtiene el nombre de una variable.|  
|[Método GetSize](icordebugvariablesymbol-getsize-method.md)|Obtiene el tamaño de una variable en bytes.|  
|[Método GetSlotIndex](icordebugvariablesymbol-getslotindex-method.md)|Obtiene el índice de ranura administrado de una variable local.|  
|[GetValue (Método)](icordebugvariablesymbol-getvalue-method.md)|Obtiene el valor de una variable como una matriz de bytes.|  
|[Método SetValue](icordebugvariablesymbol-setvalue-method.md)|Asigna el valor de una matriz de bytes a una variable.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

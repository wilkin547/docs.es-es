---
title: Interfaz ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208725"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>Interfaz ICorDebugMergedAssemblyRecord
Proporciona información acerca de un ensamblado combinado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetCulture](icordebugmergedassemblyrecord-getculture-method.md)|Obtiene la cadena de nombre de referencia cultural del ensamblado.|  
|[Método GetIndex](icordebugmergedassemblyrecord-getindex-method.md)|Obtiene el índice de prefijo del ensamblado.|  
|[Método GetPublicKey](icordebugmergedassemblyrecord-getpublickey-method.md)|Obtiene la clave pública del ensamblado.|  
|[GetPublicKeyToken (Método)](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|Obtiene el token de clave pública del ensamblado.|  
|[Método GetSimpleName](icordebugmergedassemblyrecord-getsimplename-method.md)|Obtiene el nombre simple del ensamblado.|  
|[Método GetVersion](icordebugmergedassemblyrecord-getversion-method.md)|Obtiene información de la versión del ensamblado.|  
  
## <a name="remarks"></a>Observaciones  
  
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

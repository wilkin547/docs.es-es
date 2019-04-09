---
title: Interfaz ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180471"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>Interfaz ICorDebugMergedAssemblyRecord
Proporciona información acerca de un ensamblado combinado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetCulture](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|Obtiene la cadena de nombre de referencia cultural del ensamblado.|  
|[Método GetIndex](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|Obtiene el índice de prefijo del ensamblado.|  
|[Método GetPublicKey](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|Obtiene la clave pública del ensamblado.|  
|[GetPublicKeyToken (Método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|Obtiene el token de clave pública del ensamblado.|  
|[Método GetSimpleName](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|Obtiene el nombre simple del ensamblado.|  
|[Método GetVersion](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|Obtiene información de la versión del ensamblado.|  
  
## <a name="remarks"></a>Comentarios  
  
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

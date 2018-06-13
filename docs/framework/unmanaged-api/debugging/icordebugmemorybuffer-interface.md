---
title: ICorDebugMemoryBuffer (Interfaz)
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1bc8e1206b8a82127645362cfe0a124074271c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414409"
---
# <a name="icordebugmemorybuffer-interface"></a>ICorDebugMemoryBuffer (Interfaz)
Representa un búfer en memoria.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|Obtiene el tamaño del búfer de memoria en bytes.|  
|[GetStartAddress (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|Obtiene la dirección de inicio del búfer de memoria.|  
  
## <a name="remarks"></a>Comentarios  
  
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

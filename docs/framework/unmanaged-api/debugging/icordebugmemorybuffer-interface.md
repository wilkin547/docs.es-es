---
description: 'Más información acerca de: interfaz ICorDebugMemoryBuffer'
title: Método ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 94eeb0f31c0e1c053fabbd556768fa65dda2d328
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754022"
---
# <a name="icordebugmemorybuffer-interface"></a>Método ICorDebugMemoryBuffer

Representa un búfer en memoria.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetSize](icordebugmemorybuffer-getsize-method.md)|Obtiene el tamaño del búfer de memoria en bytes.|  
|[Método GetStartAddress](icordebugmemorybuffer-getstartaddress-method.md)|Obtiene la dirección de inicio del búfer de memoria.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)

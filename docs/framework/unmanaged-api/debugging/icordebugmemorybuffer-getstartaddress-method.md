---
title: 'ICorDebugMemoryBuffer:: Getstartaddress ((método)'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1394624051baa9e7dd21e29788d5fab28332081b
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987548"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>ICorDebugMemoryBuffer:: Getstartaddress ((método)
Obtiene la dirección de inicio del búfer de memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [out] Puntero a la dirección de inicio del búfer de memoria.  
  
## <a name="remarks"></a>Comentarios  
  
> [!WARNING]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugMemoryBuffer (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

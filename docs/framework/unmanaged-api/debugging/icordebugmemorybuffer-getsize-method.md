---
title: 'ICorDebugMemoryBuffer:: (método)'
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1693860abe99884ee443be0666dfb6b485a219a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128004"
---
# <a name="icordebugmemorybuffergetsize-method"></a>ICorDebugMemoryBuffer:: (método)
Obtiene el tamaño del búfer de memoria en bytes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pcbBufferLength`  
 [out] Puntero al tamaño del búfer de memoria.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugMemoryBuffer (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 3927e57883ebe282b262cb03ececc3b2cd96fd46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123414"
---
# <a name="icordebugprocess6processstatechanged-method"></a>Método ICorDebugProcess6::ProcessStateChanged
Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que el proceso se está ejecutando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a>Parámetros  
 `change`  
 de Un miembro de la enumeración [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)  
  
## <a name="remarks"></a>Comentarios  
 El depurador llama a este método para notificar a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que el proceso se está ejecutando.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess6 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

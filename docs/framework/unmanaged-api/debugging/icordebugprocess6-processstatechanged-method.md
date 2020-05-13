---
title: Método ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 6be216741e902b15efc3a3ece95cb4a4229960e3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212859"
---
# <a name="icordebugprocess6processstatechanged-method"></a>Método ICorDebugProcess6::ProcessStateChanged
Notifica a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a>Parámetros  
 `change`  
 de Un miembro de la enumeración [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)  
  
## <a name="remarks"></a>Observaciones  
 El depurador llama a este método para notificar a [ICorDebug](icordebug-interface.md) que el proceso se está ejecutando.  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)

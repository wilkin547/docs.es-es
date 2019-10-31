---
title: 'ICorDebugExceptionDebugEvent:: GetStackPointer (método)'
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 688f5aec457298a43d95a35fdbc6e04e29a306a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084682"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a>ICorDebugExceptionDebugEvent:: GetStackPointer (método)
Obtiene el puntero de pila para este evento de depuración de la excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pStackPointer`  
 [out] Puntero a la dirección del puntero de pila para este evento de depuración de la excepción. Vea la sección Comentarios para obtener más información.  
  
## <a name="remarks"></a>Comentarios  
 El significado de este puntero de pila depende del tipo de evento, como se muestra en la tabla siguiente.  
  
|Tipo de evento.|Significado del valor `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Puntero de pila para el marco que produjo la excepción.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Puntero de pila para el marco de código de usuario más cercano al punto de la excepción generada.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Puntero de pila para el marco que contiene el controlador catch.|  
|[MANAGED_EXCEPTION_UNHANDLED](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|`pStackPointer` es **null**.|  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
 El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugExceptionDebugEvent (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

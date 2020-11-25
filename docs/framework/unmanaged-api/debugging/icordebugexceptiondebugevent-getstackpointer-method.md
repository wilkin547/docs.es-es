---
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 46906e7d3ce7f257eb776e50dc6097946eb77d1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697407"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a>ICorDebugExceptionDebugEvent::GetNativeIP (método)

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
  
|Tipo de evento|Significado del valor `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Puntero de pila para el marco que produjo la excepción.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Puntero de pila para el marco de código de usuario más cercano al punto de la excepción generada.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|Puntero de pila para el marco que contiene el controlador catch.|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|`pStackPointer` es **NULL**.|  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
 El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)

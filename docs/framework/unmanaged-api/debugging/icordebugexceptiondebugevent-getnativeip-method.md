---
title: 'ICorDebugExceptionDebugEvent:: Getnativeip ((método)'
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 42fedd20d7560dd84a2abf0efce227393035bc38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084745"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a>ICorDebugExceptionDebugEvent:: Getnativeip ((método)
Obtiene el puntero de instrucción nativo para este evento de depuración de la excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pIP`  
 [out] Puntero al puntero de instrucción para este evento de depuración de la excepción. Vea la sección Comentarios para obtener más información.  
  
## <a name="remarks"></a>Comentarios  
 El significado de este puntero de instrucción depende del tipo de evento, como se muestra en la tabla siguiente.  
  
|Tipo de evento.|Significado del valor `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Dirección de la instrucción con errores.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Dirección del código en el marco indicado por el método [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) donde se reanudaría la ejecución si no se hubiera producido ninguna excepción. La excepción puede o no puede causar un código diferente, por ejemplo, un bloque catch de una cláusula `try/catch/finally`, para ejecutar en este marco.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Dirección del código donde se iniciará la ejecución del controlador `catch` en el marco indicado por el método [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) .|  
|[MANAGED_EXCEPTION_UNHANDLED](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|`pIP` es 0.|  
  
 El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugExceptionDebugEvent (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

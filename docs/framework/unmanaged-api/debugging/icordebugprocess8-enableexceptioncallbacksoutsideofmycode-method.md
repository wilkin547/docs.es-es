---
title: Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123384"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
[Se admite en el .NET Framework 4,6 y versiones posteriores]  
  
 Habilita o deshabilita determinados tipos de devoluciones de llamada de excepción de [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `enableExceptionsOutsideOfJMC` es `false`:  
  
- Una excepción DEBUG_EXCEPTION_FIRST_CHANCE no producirá una devolución de llamada al depurador.  
  
- Una excepción DEBUG_EXCEPTION_CATCH_HANDLER_FOUND no producirá una devolución de llamada al depurador si la excepción nunca se convierte en código de usuario (es decir, la ruta de acceso de un origen de excepción a un controlador de excepciones no tiene métodos marcados como JustMyCode o JMC).  
  
 El valor predeterminado de `enableExceptionsOutsideOfJMC` es `true`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess8 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

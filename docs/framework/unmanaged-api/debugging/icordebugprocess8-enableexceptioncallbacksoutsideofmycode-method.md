---
title: Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: e54dd051f0dbd9c1964d381c2e05189c375fa66d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210142"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Método de ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
[Se admite en el .NET Framework 4,6 y versiones posteriores]  
  
 Habilita o deshabilita determinados tipos de devoluciones de llamada de excepción de [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Observaciones  
 Si el valor de `enableExceptionsOutsideOfJMC` es `false`:  
  
- Una excepción DEBUG_EXCEPTION_FIRST_CHANCE no generará una devolución de llamada al depurador.  
  
- Una excepción DEBUG_EXCEPTION_CATCH_HANDLER_FOUND no generará una devolución de llamada al depurador si la excepción nunca se convierte en código de usuario (es decir, la ruta de acceso desde el origen de una excepción al controlador de excepciones no tiene métodos marcados como JustMyCode o JMC).  
  
 El valor predeterminado de `enableExceptionsOutsideOfJMC` es `true`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz de ICorDebugProcess8](icordebugprocess8-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)

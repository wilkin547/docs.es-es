---
title: Método ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
ms.openlocfilehash: 48bab20a71144b28f24951556eb36210d7b6aebf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123429"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a>Método ICorDebugProcess6::MarkDebuggerAttached
Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fIsAttached`  
 `true` si el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> debe indicar que hay un depurador asociado; de lo contrario, `false`.  
  
## <a name="return-value"></a>Valor devuelto  
 El método puede devolver los valores enumerados en la siguiente tabla.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`S_OK`|El código que se va a depurar se ha actualizado correctamente.|  
|`CORDBG_E_MODULE_NOT_LOADED`|El ensamblado que contiene el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> no está cargado, o hay algún otro error (como metadatos que faltan) que está impidiendo que se reconozca.<br /><br /> Este error es habitual y no tiene repercusión alguna. Deberá llamar al método de nuevo cuando se carguen más ensamblados.|  
|Otros valores de error de `HRESULT`.|Otros valores probablemente indiquen que el depurador o los componentes del compilador no funcionan correctamente.|  
  
## <a name="remarks"></a>Comentarios  
  
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

---
title: Método ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f21ea449cf30bd9c07b7ae9b382877ce18f102d9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736415"
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
  
|Valor devuelto|DESCRIPCIÓN|  
|------------------|-----------------|  
|`S_OK`|El código que se va a depurar se ha actualizado correctamente.|  
|`CORDBG_E_MODULE_NOT_LOADED`|El ensamblado que contiene el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> no está cargado, o hay algún otro error (como metadatos que faltan) que está impidiendo que se reconozca.<br /><br /> Este error es habitual y no tiene repercusión alguna. Deberá llamar al método de nuevo cuando se carguen más ensamblados.|  
|Otros valores de error de `HRESULT`.|Otros valores probablemente indiquen que el depurador o los componentes del compilador no funcionan correctamente.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess6 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

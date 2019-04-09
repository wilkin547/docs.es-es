---
title: Método ICorDebugProcess6::MarkDebuggerAttached
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15e2e94ac4e30fbdb375175148a5b448c51821f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128029"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a>Método ICorDebugProcess6::MarkDebuggerAttached
Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fIsAttached`  
 `true` Si el <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> método debería indicar que se adjunta un depurador; `false` en caso contrario.  
  
## <a name="return-value"></a>Valor devuelto  
 El método puede devolver los valores enumerados en la siguiente tabla.  
  
|Valor devuelto|Descripción|  
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

- [Interfaz ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

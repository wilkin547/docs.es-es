---
title: ICorDebugManagedCallback::UpdateModuleSymbols (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 1f5b413ffbbc8fccbea38f23d8c87d40e010dd37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130616"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a>ICorDebugManagedCallback::UpdateModuleSymbols (Método)
Notifica al depurador que los símbolos para un módulo de Common Language Runtime han cambiado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el módulo en el que los símbolos han cambiado.  
  
 `pModule`  
 de Un puntero a un objeto ICorDebugModule que representa el módulo en el que los símbolos han cambiado.  
  
 `pSymbolStream`  
 de Puntero a un objeto de `IStream` COM de Win32 que contiene los símbolos modificados.  
  
## <a name="remarks"></a>Comentarios  
 Este método proporciona una oportunidad para actualizar la vista del depurador de los símbolos de un módulo llamando a [ISymUnmanagedReader:: UpdateSymbolStore (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) o [ISymUnmanagedReader:: replacesymbolstore (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).  
  
 Esta devolución de llamada puede producirse varias veces para el mismo módulo.  
  
 Un depurador debe intentar enlazar puntos de interrupción sin enlazar en el nivel de origen.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

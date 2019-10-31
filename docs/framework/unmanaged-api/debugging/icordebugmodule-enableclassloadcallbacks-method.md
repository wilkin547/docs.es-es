---
title: ICorDebugModule::EnableClassLoadCallbacks (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139216"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks (Método)
Controla si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) para este módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bClassLoadCallbacks`  
 de Establezca este valor en `true` para permitir que el Common Language Runtime (CLR) llame a los métodos `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` cuando se produzcan los eventos asociados.  
  
 El valor predeterminado es `false` para los módulos no dinámicos. El valor siempre es `true` para los módulos dinámicos y no se puede cambiar.  
  
## <a name="remarks"></a>Comentarios  
 Las devoluciones de llamada `ICorDebugManagedCallback::LoadClass` y `ICorDebugManagedCallback::UnloadClass` siempre están habilitadas para los módulos dinámicos y no se pueden deshabilitar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

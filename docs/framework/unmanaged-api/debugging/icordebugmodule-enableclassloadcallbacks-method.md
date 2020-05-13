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
ms.openlocfilehash: 1ca3adf30ad633fcfb10a4b43a435698d2899597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213535"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks (Método)
Controla si se llama a las devoluciones de llamada [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) y [ICorDebugManagedCallback:: UnloadClass (](icordebugmanagedcallback-unloadclass-method.md) para este módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bClassLoadCallbacks`  
 de Establezca este valor en `true` para permitir que el Common Language Runtime (CLR) llame a `ICorDebugManagedCallback::LoadClass` los `ICorDebugManagedCallback::UnloadClass` métodos y cuando se produzcan los eventos asociados.  
  
 El valor predeterminado es `false` para los módulos no dinámicos. El valor siempre es `true` para los módulos dinámicos y no se puede cambiar.  
  
## <a name="remarks"></a>Observaciones  
 Las `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` devoluciones de llamada y siempre están habilitadas para los módulos dinámicos y no se pueden deshabilitar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

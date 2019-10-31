---
title: ICorDebugManagedCallback::CreateProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: d773368c85fd42fd169109cf1c7e6635705ebb7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090226"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a>ICorDebugManagedCallback::CreateProcess (Método)
Notifica al depurador cuando un proceso se ha adjuntado o Iniciado por primera vez.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pProcess`  
 de Un puntero a un objeto ICorDebugProcess que representa el proceso que se ha adjuntado o iniciado.  
  
## <a name="remarks"></a>Comentarios  
 No se llama a este método hasta que se inicializa el Common Language Runtime. La mayoría de los métodos [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) devolverán CORDBG_E_NOTREADY antes de la devolución de llamada `CreateProcess`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

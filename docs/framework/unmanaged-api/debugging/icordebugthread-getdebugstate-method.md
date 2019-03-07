---
title: ICorDebugThread::GetDebugState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68df19120f2e0b45e73f9d5e137afc8a5e7ac513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489896"
---
# <a name="icordebugthreadgetdebugstate-method"></a>ICorDebugThread::GetDebugState (Método)
Obtiene el estado de depuración actual de este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pState`  
 [out] Un puntero a una combinación bit a bit de valores de enumeración CorDebugThreadState que describe el estado de depuración actual de este subproceso.  
  
## <a name="remarks"></a>Comentarios  
 Si actualmente se detiene el proceso, `pState` representa el estado de depuración que existiría para este subproceso si el proceso se puede continuar, no el estado actual real de este subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

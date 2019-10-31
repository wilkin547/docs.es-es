---
title: ICorDebugProcess::IsOSSuspended (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: 21da69d4bff0f17eb607dda45fb7dbafea8c59f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128768"
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended (Método)
Obtiene un valor que indica si el subproceso especificado se ha suspendido como resultado de que el depurador detenga este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Parámetros  
 `threadID`  
 de IDENTIFICADOR del subproceso en cuestión.  
  
 `pbSuspended`  
 enuncia Un puntero a un valor booleano que es `true` si se ha suspendido el subproceso especificado; de lo contrario, *`pbSuspended` es `false`.  
  
## <a name="remarks"></a>Comentarios  
 Cuando el subproceso especificado se ha suspendido como resultado de que el depurador detenga este proceso, el recuento de suspensión de Win32 del subproceso especificado se incrementa en uno. Es posible que la interfaz de usuario (UI) del depurador desee tener en cuenta esta información si muestra el recuento de suspensiones del sistema operativo (SO) del subproceso al usuario.  
  
 El método `IsOSSuspended` solo tiene sentido en el contexto de la depuración no administrada. Durante la depuración administrada, los subprocesos se suspenden de forma cooperativa en lugar de suspender el sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

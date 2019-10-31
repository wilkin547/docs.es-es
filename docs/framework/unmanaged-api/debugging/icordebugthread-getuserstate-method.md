---
title: ICorDebugThread::GetUserState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: f3511ff5ee9b9221037c64a5e17d61f6bf52e5f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133406"
---
# <a name="icordebugthreadgetuserstate-method"></a>ICorDebugThread::GetUserState (Método)
Obtiene el estado de usuario actual de esta ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pState`  
 enuncia Un puntero a una combinación bit a bit de los valores de enumeración de CorDebugUserState (que describen el estado de usuario actual de este subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El estado de usuario del subproceso es el estado del subproceso cuando lo examina el programa que se está depurando. Un subproceso puede tener varios bits de estado establecidos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

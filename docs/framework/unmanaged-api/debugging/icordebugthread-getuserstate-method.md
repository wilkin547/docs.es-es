---
description: 'Más información acerca de: ICorDebugThread:: Getuserstate ((método)'
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
ms.openlocfilehash: b63b474525534f9e934954ebe660691db90b8b67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658872"
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
  
## <a name="remarks"></a>Observaciones  

 El estado de usuario del subproceso es el estado del subproceso cuando lo examina el programa que se está depurando. Un subproceso puede tener varios bits de estado establecidos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

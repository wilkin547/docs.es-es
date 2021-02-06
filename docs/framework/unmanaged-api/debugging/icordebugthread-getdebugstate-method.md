---
description: 'Más información acerca de: ICorDebugThread:: Getdebugstate ((método)'
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
ms.openlocfilehash: 86534dded9b8e931fe2a7e44f1c95dc2ec7b6f0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659158"
---
# <a name="icordebugthreadgetdebugstate-method"></a>ICorDebugThread::GetDebugState (Método)

Obtiene el estado de depuración actual de este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pState`  
 enuncia Un puntero a una combinación bit a bit de valores de enumeración de CorDebugThreadState (que describe el estado de depuración actual de este subproceso.  
  
## <a name="remarks"></a>Observaciones  

 Si el proceso está detenido actualmente, `pState` representa el estado de depuración que existirá para este subproceso si el proceso tuviera que continuar, no el estado actual real de este subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
title: ICorDebugProcess2::GetThreadForTaskID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
ms.openlocfilehash: 89be29c770098d92ce3c47f7c45b1bb8580f2edb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213522"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a>ICorDebugProcess2::GetThreadForTaskID (Método)
Obtiene el subproceso en el que se está ejecutando la tarea con el identificador especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `taskid`  
 de Identificador de la tarea.  
  
 `ppThread`  
 enuncia Puntero a la dirección de un objeto ICorDebugThread2 que representa el subproceso que se va a recuperar.  
  
## <a name="remarks"></a>Observaciones  
 El host puede establecer el identificador de tarea mediante el método [ICLRTask:: settaskidentifier (](../hosting/iclrtask-settaskidentifier-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

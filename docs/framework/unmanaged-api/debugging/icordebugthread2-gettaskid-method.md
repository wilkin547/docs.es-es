---
title: ICorDebugThread2::GetTaskID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1272df17a9a9a500b84f62914811b8d109bf3cdd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768952"
---
# <a name="icordebugthread2gettaskid-method"></a>ICorDebugThread2::GetTaskID (Método)
Obtiene el identificador de la tarea que se ejecuta en este subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pTaskId`  
 [out] Un puntero al identificador de la tarea que se ejecuta en el subproceso representado por este objeto ICorDebugThread2.  
  
## <a name="remarks"></a>Comentarios  
 Solo se puede ejecutar una tarea en el subproceso si el subproceso está asociado con una conexión. `GetTaskID` Devuelve cero `pTaskId` si el subproceso no está asociado con una conexión.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

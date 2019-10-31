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
ms.openlocfilehash: d5f2838007504e56ad44614a6778083be046629f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140075"
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
 enuncia Puntero al identificador de la tarea que se ejecuta en el subproceso representado por este objeto ICorDebugThread2.  
  
## <a name="remarks"></a>Comentarios  
 Una tarea solo se puede ejecutar en el subproceso si el subproceso está asociado a una conexión. `GetTaskID` devuelve cero en `pTaskId` si el subproceso no está asociado a una conexión.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

---
title: ICorDebugThread::GetActiveFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: d623893bd77e46832b0bd823ed60c23e4eee29ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133541"
---
# <a name="icordebugthreadgetactiveframe-method"></a>ICorDebugThread::GetActiveFrame (Método)
Obtiene un puntero de interfaz al marco activo (más reciente) en este objeto ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppFrame`  
 enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFrame que representa un marco.  
  
## <a name="remarks"></a>Comentarios  
 El parámetro `ppFrame` es NULL si no hay ningún fotograma activo actualmente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

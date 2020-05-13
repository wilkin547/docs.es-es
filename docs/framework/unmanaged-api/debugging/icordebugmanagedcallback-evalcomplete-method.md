---
title: ICorDebugManagedCallback::EvalComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
ms.openlocfilehash: 0431b54997c9889e2b3206392e86e4dcde45ffb3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212456"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a>ICorDebugManagedCallback::EvalComplete (Método)
Notifica al depurador que se ha completado una evaluación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se realizó la evaluación.  
  
 `pThread`  
 de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se realizó la evaluación.  
  
 `pEval`  
 de Un puntero a un objeto ICorDebugEval que representa el código que llevó a cabo la evaluación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)

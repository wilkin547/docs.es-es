---
title: ICorDebugThread::CreateEval (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480668"
---
# <a name="icordebugthreadcreateeval-method"></a>ICorDebugThread::CreateEval (Método)
Crea un objeto ICorDebugEval que recopila y expone la funcionalidad de esta instancia de ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppEval`  
 [out] Un puntero a la dirección de un `ICorDebugEval` objeto que recopila y expone la funcionalidad de este subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El objeto de evaluación insertará una nueva cadena en el subproceso antes de realizar el cálculo. Esto interrumpe el cálculo están llevando a cabo en el subproceso hasta que se complete la evaluación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
title: ICorDebugFunction2::GetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 360434fe6e08804d8c80c4ea36d585209cc6761a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137819"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>ICorDebugFunction2::GetJMCStatus (Método)
Obtiene un valor que indica si la función representada por este objeto ICorDebugFunction2 está marcada como código de usuario.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbIsJustMyCode`  
 enuncia Un puntero a un valor booleano que se `true`, si esta función está marcada como código de usuario; de lo contrario, el valor es `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si no se puede depurar la función representada por este `ICorDebugFunction2`, `pbIsJustMyCode` siempre se `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

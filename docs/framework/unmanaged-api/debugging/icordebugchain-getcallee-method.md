---
title: ICorDebugChain::GetCallee (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f050a3d9d37e43713c40896fb162bcf9932c6512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee (Método)
Obtiene la cadena que se llama a esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppChain`  
 [out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada. Si esta cadena se está ejecutando actualmente (es decir, si esta cadena no está esperando una cadena de llamada devolver), `ppChain` será null.  
  
## <a name="remarks"></a>Comentarios  
 Esta cadena esperará la cadena de llamada devolver antes de que reanuda la ejecución. La cadena de llamada puede estar en otro subproceso en el caso de llamadas de calcular las referencias entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

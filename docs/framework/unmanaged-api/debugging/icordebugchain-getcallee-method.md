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
ms.openlocfilehash: a28da34cd3080826f346b8957aa6ba38258b924f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730128"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee (Método)

Obtiene la cadena a la que llamó esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppChain`  
 enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena a la que se ha llamado. Si esta cadena se está ejecutando actualmente (es decir, si esta cadena no está esperando a que devuelva una cadena llamada), `ppChain` será null.  
  
## <a name="remarks"></a>Comentarios  

 Esta cadena esperará a que se devuelva la cadena llamada antes de reanudar la ejecución. La cadena llamada puede estar en otro subproceso en el caso de las llamadas de serialización entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

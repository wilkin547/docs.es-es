---
title: ICorDebugChain::GetRegisterSet (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: a3f02af1a0de9fcd7b3db1e49ef0d78af3395d2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719663"
---
# <a name="icordebugchaingetregisterset-method"></a>ICorDebugChain::GetRegisterSet (Método)

Obtiene el conjunto de registros para la parte activa de esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppRegisters`  
 enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para la parte activa de esta cadena.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

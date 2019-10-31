---
title: ICorDebugChain::GetActiveFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: 03cb1556ee971124ed4c591f38d9f892fc7df7b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192155"
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame (Método)
Obtiene el marco activo (es decir, el más reciente) de la cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppFrame`  
 enuncia Puntero a la dirección de un objeto ICorDebugFrame que representa el marco activo (es decir, el más reciente) en la cadena.  
  
## <a name="remarks"></a>Comentarios  
 Si no hay ningún marco de pila administrado disponible, `ppFrame` se establece en NULL.  
  
 Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null. Los marcos activos no estarán disponibles para las cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED y, para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT. Vea la enumeración CorDebugChainReason (.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

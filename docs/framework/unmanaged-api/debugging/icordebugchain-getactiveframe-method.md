---
description: 'Más información sobre: ICorDebugChain:: GetActiveFrame ((método)'
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
ms.openlocfilehash: d46906d9d6c671880d9446d889cdf9f83f3b4366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661429"
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
  
## <a name="remarks"></a>Observaciones  

 Si no hay ningún marco de pila administrado disponible, `ppFrame` se establece en NULL.  
  
 Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null. Los marcos activos no estarán disponibles para las cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED, y para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT. Vea la enumeración CorDebugChainReason (.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

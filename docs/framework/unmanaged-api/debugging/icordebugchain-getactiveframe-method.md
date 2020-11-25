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
ms.openlocfilehash: daecd216b4d7e9c23336b8956c13735549be901b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730141"
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
  
 Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null. Los marcos activos no estarán disponibles para las cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED, y para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT. Vea la enumeración CorDebugChainReason (.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

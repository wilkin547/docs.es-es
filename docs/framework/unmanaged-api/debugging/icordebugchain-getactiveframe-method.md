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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a104d4d3cc74a6c1cb343818c9b0b3e8978b97df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402804"
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame (Método)
Obtiene el activo (es decir, más reciente) marco en la cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppFrame`  
 [out] Un puntero a la dirección de un objeto ICorDebugFrame que representa el activo (es decir, más reciente) marco en la cadena.  
  
## <a name="remarks"></a>Comentarios  
 Si está disponible, ningún marco de pila administrado `ppFrame` se establece en null.  
  
 Si el marco activo no está disponible, la llamada se realizará correctamente y `ppFrame` será null. Marcos activa no estarán disponibles para cadenas iniciadas debido a CHAIN_ENTER_UNMANAGED y para algunas cadenas iniciadas debido a CHAIN_CLASS_INIT. Vea el CorDebugChainReason (enumeración).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

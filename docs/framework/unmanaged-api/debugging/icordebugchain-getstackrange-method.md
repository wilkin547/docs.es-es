---
title: ICorDebugChain::GetStackRange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: d9430c5a1f37a0507b383ea5437f7d7fed706c43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123862"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange (Método)
Obtiene el intervalo de direcciones del segmento de pila para esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pStart`  
 enuncia Un puntero a un valor de `CORDB_ADDRESS` que es la dirección inicial del segmento de pila.  
  
 `pEnd`  
 enuncia Un puntero a un valor de `CORDB_ADDRESS` que es la dirección final del segmento de pila.  
  
## <a name="remarks"></a>Comentarios  
 El intervalo numérico solo es significativo para la comparación de las ubicaciones de los marcos de pila. No puede hacer ninguna suposición sobre lo que realmente se almacena en la pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

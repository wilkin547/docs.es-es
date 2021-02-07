---
description: 'Más información sobre: ICorDebugChain:: GetThread ((método)'
title: ICorDebugChain::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: 090cb40c3681792ce4a30cd342e65dc02ac3f381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694929"
---
# <a name="icordebugchaingetthread-method"></a>ICorDebugChain::GetThread (Método)

Obtiene el subproceso físico del que forma parte esta cadena de llamadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppThread`  
 enuncia Un puntero a un objeto ICorDebugThread que representa el subproceso físico del que forma parte esta cadena de llamadas.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

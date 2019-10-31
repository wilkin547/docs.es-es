---
title: ICorDebugEval2::RudeAbort (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: a486935d5d53a6fc7d862160ed1186c5774814c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084794"
---
# <a name="icordebugeval2rudeabort-method"></a>ICorDebugEval2::RudeAbort (Método)
Anula el cálculo que este `ICorDebugEval2` está realizando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Comentarios  
 `RudeAbort` no libera los bloqueos que incluye el evaluador, por lo que deja la sesión de depuración en un estado no seguro. Llame a este método con sumo cuidado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

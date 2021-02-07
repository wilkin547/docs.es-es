---
description: 'Más información sobre: ICorDebugEval2:: RudeAbort ((método)'
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
ms.openlocfilehash: 2835fd635da007b5ee3f0e642b77f3954945f168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693517"
---
# <a name="icordebugeval2rudeabort-method"></a>ICorDebugEval2::RudeAbort (Método)

Anula el cálculo que `ICorDebugEval2` está realizando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a>Observaciones  

 `RudeAbort` no libera los bloqueos que mantiene el evaluador, por lo que deja la sesión de depuración en un estado no seguro. Llame a este método con sumo cuidado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

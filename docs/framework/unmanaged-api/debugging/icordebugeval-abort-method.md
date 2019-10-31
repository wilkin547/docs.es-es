---
title: ICorDebugEval::Abort (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: 78402e5e099815fe309618e692285de91b8b29f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124237"
---
# <a name="icordebugevalabort-method"></a>ICorDebugEval::Abort (Método)
Anula el cálculo que este objeto ICorDebugEval está realizando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a>Comentarios  
 Si la evaluación está anidada y no es la más reciente, puede producirse un error en el método `Abort`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

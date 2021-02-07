---
description: 'Más información acerca de: ICorDebugEval:: ABORT (método)'
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
ms.openlocfilehash: d61cb0d696a8a134d992bc8dbbfdb61103ef469f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694323"
---
# <a name="icordebugevalabort-method"></a>ICorDebugEval::Abort (Método)

Anula el cálculo que este objeto ICorDebugEval está realizando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a>Observaciones  

 Si la evaluación está anidada y no es la más reciente, `Abort` puede producirse un error en el método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

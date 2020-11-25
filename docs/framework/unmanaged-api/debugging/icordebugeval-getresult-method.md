---
title: ICorDebugEval::GetResult (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 86c017f581c7b980b8b0cb8bd7bdc1b0aa439afe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705836"
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult (Método)

Obtiene los resultados de esta evaluación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppResult`  
 enuncia Puntero a la dirección de un objeto ICorDebugValue que representa los resultados de esta evaluación, si la evaluación se completa con normalidad.  
  
## <a name="remarks"></a>Comentarios  

 El `GetResult` método es válido solo después de que se complete la evaluación.  
  
 Si la evaluación se completa normalmente, `ppResult` especifica los resultados. Si finaliza con una excepción, el resultado es la excepción que se produce. Si la evaluación era para un nuevo objeto, el resultado es la referencia al nuevo objeto.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

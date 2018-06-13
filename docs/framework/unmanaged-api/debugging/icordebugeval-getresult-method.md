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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e160eddf667b542929c8dd3790de666a8e8bb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413064"
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult (Método)
Obtiene los resultados de esta evaluación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppResult`  
 [out] Puntero a la dirección de un objeto ICorDebugValue que representa los resultados de esta evaluación, si la evaluación se completa con normalidad.  
  
## <a name="remarks"></a>Comentarios  
 El `GetResult` método es válido solo una vez completada la evaluación.  
  
 Si la evaluación se completa con normalidad, `ppResult` especifica los resultados. Si finaliza con una excepción, el resultado es la excepción producida. Si la evaluación era para un nuevo objeto, el resultado es la referencia al nuevo objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

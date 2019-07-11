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
ms.openlocfilehash: b12ba5ad5c85643d1f4c91585cf7abca210d22bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752940"
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
 [out] Puntero a la dirección de un objeto ICorDebugValue que representa los resultados de esta evaluación, si la evaluación se completa con normalidad.  
  
## <a name="remarks"></a>Comentarios  
 El `GetResult` método es válido solo una vez completada la evaluación.  
  
 Si la evaluación se completa con normalidad, `ppResult` especifica los resultados. Si finaliza con una excepción, el resultado es la excepción. Si la evaluación fue para un nuevo objeto, el resultado es la referencia al nuevo objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

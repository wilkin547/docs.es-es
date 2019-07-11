---
title: ICorDebugEval::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24bc096a0ba01c58aa963d69fa46a1d1bbe8be75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752908"
---
# <a name="icordebugevalgetthread-method"></a>ICorDebugEval::GetThread (Método)
Obtiene el subproceso en el que se está ejecutando o ejecutará esta evaluación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppThread`  
 [out] Un puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

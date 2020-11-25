---
title: ICorDebugFunction::GetModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
ms.openlocfilehash: 5fad8b56b783748e23c8adc4aee0e1bf3450e243
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696133"
---
# <a name="icordebugfunctiongetmodule-method"></a>ICorDebugFunction::GetModule (Método)

Obtiene el módulo en el que se define esta función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppModule`  
 enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta función.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

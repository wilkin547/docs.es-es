---
title: ICorDebugFunctionBreakpoint::GetOffset (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
ms.openlocfilehash: 0f6fe5d7eb5926d48809bb6490ba75df9d4a5033
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213158"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a>ICorDebugFunctionBreakpoint::GetOffset (Método)
Obtiene el desplazamiento del punto de interrupción dentro de la función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pnOffset`  
 enuncia Puntero al desplazamiento del punto de interrupción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

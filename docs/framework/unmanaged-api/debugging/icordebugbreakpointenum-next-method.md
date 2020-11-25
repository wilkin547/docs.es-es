---
title: ICorDebugBreakpointEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
ms.openlocfilehash: 14c89e808ea8e41bbee46a59a60bc1876f3800d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730193"
---
# <a name="icordebugbreakpointenumnext-method"></a>ICorDebugBreakpointEnum::Next (Método)

Obtiene el número especificado de instancias de ICorDebugBreakpoint de la enumeración, comenzando en la posición actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `celt`  
 de El número de `ICorDebugBreakpoint` instancias que se van a recuperar.  
  
 `breakpoints`  
 enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugBreakpoint` objeto que representa un punto de interrupción.  
  
 `pceltFetched`  
 enuncia Puntero al número de `ICorDebugBreakpoint` instancias devueltas realmente. Este valor puede ser null si `celt` es uno.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
description: 'Más información sobre: ICorDebugFunctionBreakpoint:: GetFunction ((método)'
title: ICorDebugFunctionBreakpoint::GetFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
ms.openlocfilehash: 1e407acda81e5e6397da003a9b91a48d4d171e5d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754100"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a>ICorDebugFunctionBreakpoint::GetFunction (Método)

Obtiene un puntero de interfaz a una ICorDebugFunction que hace referencia a la función en la que se establece el punto de interrupción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppFunction`  
 enuncia Puntero a la dirección de la función en la que se establece el punto de interrupción.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
title: ICorDebugCode::CreateBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
ms.openlocfilehash: b02fb0a18bfbc2e93ec204706ca1f17dde5d8c8a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125709"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>ICorDebugCode::CreateBreakpoint (Método)
Crea un punto de interrupción en este segmento de código en el desplazamiento especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `offset`  
 de Desplazamiento en el que se va a crear el punto de interrupción.  
  
 `ppBreakpoint`  
 enuncia Puntero a la dirección de un objeto "ICorDebugFunctionBreakpoint" que representa el punto de interrupción.  
  
## <a name="remarks"></a>Comentarios  
 Antes de que el punto de interrupción esté activo, debe agregarse al objeto de proceso.  
  
 Si este código es código del lenguaje intermedio de Microsoft (MSIL) y hay una versión nativa y compilada Just-in-Time (JIT) del código, el punto de interrupción se aplicará también en el código compilado JIT. (Lo mismo sucede si el código se compila posteriormente).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1173091a5f2d8814747c93f827150afe39b8b309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcodecreatebreakpoint-method"></a>ICorDebugCode::CreateBreakpoint (Método)
Crea un punto de interrupción en este segmento de código en el desplazamiento especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `offset`  
 [in] Desplazamiento en el que se va a crear el punto de interrupción.  
  
 `ppBreakpoint`  
 [out] Un puntero a la dirección de un objeto de "ICorDebugFunctionBreakpoint" que representa el punto de interrupción.  
  
## <a name="remarks"></a>Comentarios  
 Antes de que el punto de interrupción está activo, se debe agregar al objeto de proceso.  
  
 Si este código es código de lenguaje intermedio (MSIL) de Microsoft y no hay un just-in-time (JIT)-versión nativa compilada del código, el punto de interrupción se aplicará en el código compilado JIT. (El mismo es verdadero si el código compilado JIT más adelante).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 

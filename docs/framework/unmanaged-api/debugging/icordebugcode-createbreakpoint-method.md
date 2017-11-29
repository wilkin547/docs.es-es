---
title: "ICorDebugCode::CreateBreakpoint (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 214d032129613230b8c55cdd286ea637227a626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 

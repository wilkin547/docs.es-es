---
title: ICorDebugILFrame::GetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d7eca3c2825707c9190436377bba7e4bb0d5447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757974"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP (Método)
Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que se describe cómo se obtuvo el valor del puntero de instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pnOffset`  
 [out] El valor del puntero de instrucción.  
  
 `pMappingResult`  
 [out] Un puntero a una combinación bit a bit de los valores de enumeración CorDebugMappingResult que describen cómo se obtuvo el valor del puntero de instrucción.  
  
## <a name="remarks"></a>Comentarios  
 El valor del puntero de instrucción es el desplazamiento del marco de pila en código de lenguaje intermedio (MSIL) de Microsoft de la función. Si el marco de pila está activo, esta dirección es la siguiente instrucción que se va a ejecutar. Si el marco de pila no está activo, esta dirección es la siguiente instrucción que se ejecutará cuando se reactiva el marco de pila.  
  
 Si este marco es un marco compilado de just-in-time (JIT), el valor del puntero de instrucción se determinará mediante la asignación hacia atrás desde el puntero de instrucción nativo real, por lo que puede ser el valor sólo aproximado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

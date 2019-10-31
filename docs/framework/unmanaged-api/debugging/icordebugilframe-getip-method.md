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
ms.openlocfilehash: 7e1605eede55360e72d65da6744bc1dcce4f107f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130991"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP (Método)
Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pnOffset`  
 enuncia Valor del puntero de instrucción.  
  
 `pMappingResult`  
 enuncia Puntero a una combinación bit a bit de los valores de enumeración de CorDebugMappingResult (que describen cómo se obtuvo el valor del puntero de instrucción.  
  
## <a name="remarks"></a>Comentarios  
 El valor del puntero de instrucción es el desplazamiento del marco de pila en el código del lenguaje intermedio de Microsoft (MSIL) de la función. Si el marco de pila está activo, esta dirección es la siguiente instrucción que se va a ejecutar. Si el marco de pila no está activo, esta dirección es la siguiente instrucción que se debe ejecutar cuando se reactive el marco de pila.  
  
 Si este marco es un marco compilado Just-in-Time (JIT), el valor del puntero de instrucción estará determinado por la asignación hacia atrás desde el puntero de instrucción nativo real, por lo que el valor puede ser solo aproximado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

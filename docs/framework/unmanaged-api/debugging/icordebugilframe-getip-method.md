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
ms.openlocfilehash: 7a7b8985e7580282d0e38205f9b1d6078f86cee6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988616"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP (Método)
Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que se describe cómo se obtuvo el valor del puntero de instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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

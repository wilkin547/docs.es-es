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
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178821"
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
 [fuera] El valor del puntero de instrucción.  
  
 `pMappingResult`  
 [fuera] Un puntero a una combinación bit a bit de la CorDebugMappingResult valores de enumeración que describen cómo se obtuvo el valor del puntero de instrucción.  
  
## <a name="remarks"></a>Observaciones  
 El valor del puntero de instrucción es el desplazamiento del marco de pila en el código de lenguaje intermedio de Microsoft (MSIL) de Microsoft de la función. Si el marco de pila está activo, esta dirección es la siguiente instrucción que se debe ejecutar. Si el marco de pila no está activo, esta dirección es la siguiente instrucción que se debe ejecutar cuando se reactiva el marco de pila.  
  
 Si este fotograma es un fotograma compilado Just-In-Time (JIT), el valor del puntero de instrucción se determinará mediante la asignación hacia atrás desde el puntero de instrucción nativo real, por lo que el valor puede ser solo aproximado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

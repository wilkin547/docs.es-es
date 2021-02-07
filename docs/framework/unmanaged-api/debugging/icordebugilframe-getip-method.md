---
description: 'Más información acerca de: ICorDebugILFrame:: GetIP (método)'
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
ms.openlocfilehash: f3977d4fbe57b24e7b98b7a597b0db7ad171eb1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691879"
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
  
## <a name="remarks"></a>Observaciones  

 El valor del puntero de instrucción es el desplazamiento del marco de pila en el código del lenguaje intermedio de Microsoft (MSIL) de la función. Si el marco de pila está activo, esta dirección es la siguiente instrucción que se va a ejecutar. Si el marco de pila no está activo, esta dirección es la siguiente instrucción que se debe ejecutar cuando se reactive el marco de pila.  
  
 Si este marco es un marco compilado Just-in-Time (JIT), el valor del puntero de instrucción estará determinado por la asignación hacia atrás desde el puntero de instrucción nativo real, por lo que el valor puede ser solo aproximado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

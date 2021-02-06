---
description: 'Más información sobre: ICorDebugThread2:: GetActiveFunctions ((método)'
title: ICorDebugThread2::GetActiveFunctions (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
ms.openlocfilehash: 841e8ff17f15cfb14e1c1bf65c651a5177db2eaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658768"
---
# <a name="icordebugthread2getactivefunctions-method"></a>ICorDebugThread2::GetActiveFunctions (Método)

Obtiene información sobre la función activa en cada uno de los marcos de este subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cFunctions`  
 [in] Tamaño de la matriz `pFunctions`.  
  
 `pcFunctions`  
 enuncia Puntero al número de objetos devueltos en la `pFunctions` matriz. El número de objetos devueltos será igual al número de Marcos administrados en la pila.  
  
 `pFunctions`  
 [in, out] Matriz de objetos COR_ACTIVE_FUNCTION, cada uno de los cuales contiene información sobre las funciones activas de los marcos de este subproceso.  
  
 El primer elemento se usará para el marco hoja y así sucesivamente hasta la raíz de la pila.  
  
## <a name="remarks"></a>Observaciones  

 Si `pFunctions` es null en la entrada, `GetActiveFunctions` solo devuelve el número de funciones que se encuentran en la pila. Es decir, si `pFunctions` es null en la entrada, `GetActiveFunctions` solo devuelve un valor en `pcFunctions` .  
  
 El `GetActiveFunctions` método está pensado como una optimización para obtener la misma información de los marcos de un seguimiento de la pila e incluye solo los fotogramas que habrían tenido un objeto ICorDebugILFrame para ellos en el seguimiento de la pila completa.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

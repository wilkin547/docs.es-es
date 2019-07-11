---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdf3998d7430348cb71af8e7dd75cf2203d380ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769036"
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
 [out] Un puntero al número de objetos devueltos en la `pFunctions` matriz. El número de objetos devueltos será igual al número de marcos administrados en la pila.  
  
 `pFunctions`  
 [in, out] Una matriz de objetos COR_ACTIVE_FUNCTION, cada uno de los cuales contiene información sobre las funciones activas en los cuadros de este subproceso.  
  
 El primer elemento se utilizará para el marco de hoja y así sucesivamente de nuevo a la raíz de la pila.  
  
## <a name="remarks"></a>Comentarios  
 Si `pFunctions` es null en la entrada, `GetActiveFunctions` devuelve sólo el número de funciones que están en la pila. Es decir, si `pFunctions` es null en la entrada, `GetActiveFunctions` devuelve un valor únicamente en `pcFunctions`.  
  
 El `GetActiveFunctions` método está pensado como una optimización a través de obtener la misma información de marcos de pila del seguimiento e incluye sólo los fotogramas que habría tenido un objeto ICorDebugILFrame para ellos en el seguimiento de pila completa.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

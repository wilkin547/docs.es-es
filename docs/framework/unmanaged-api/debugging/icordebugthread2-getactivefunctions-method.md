---
title: "ICorDebugThread2::GetActiveFunctions (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2.GetActiveFunctions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecd9446f642011b21f784019f583f49e3a70433a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2getactivefunctions-method"></a>ICorDebugThread2::GetActiveFunctions (Método)
Obtiene información sobre la función activa en cada uno de los marcos de este subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cFunctions`  
 [in] Tamaño de la matriz `pFunctions`.  
  
 `pcFunctions`  
 [out] Un puntero al número de objetos devueltos en la `pFunctions` matriz. El número de objetos devueltos será igual al número de marcos administrados en la pila.  
  
 `pFunctions`  
 [entrada, salida] Una matriz de objetos COR_ACTIVE_FUNCTION, cada uno de los cuales contiene información sobre las funciones activas en los marcos de este subproceso.  
  
 El primer elemento se utilizará para el marco de hoja y así sucesivamente atrás a la raíz de la pila.  
  
## <a name="remarks"></a>Comentarios  
 Si `pFunctions` es null en la entrada, `GetActiveFunctions` devuelve solo el número de funciones que están en la pila. Es decir, si `pFunctions` es null en la entrada, `GetActiveFunctions` devuelve un valor en `pcFunctions`.  
  
 El `GetActiveFunctions` método está pensado como una optimización respecto a la obtención de la misma información de los cuadros en un seguimiento de pila y solamente incluye los cuadros que habría tenido un objeto ICorDebugILFrame para ellos en el seguimiento de pila completo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

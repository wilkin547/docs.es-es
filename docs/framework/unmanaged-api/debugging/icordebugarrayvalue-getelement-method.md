---
title: ICorDebugArrayValue::GetElement (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be7eaeccb53e8b180aeb9492cd887f952bbaea5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485309"
---
# <a name="icordebugarrayvaluegetelement-method"></a>ICorDebugArrayValue::GetElement (Método)
Obtiene el valor del elemento de matriz determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cdim`  
 [in] El número de dimensiones de esta `ICorDebugArrayValue` objeto.  
  
 Este valor también es el tamaño de la `indices` matriz porque su tamaño es igual al número de dimensiones de la `ICorDebugArrayValue` objeto.  
  
 `indices`  
 [in] Una matriz de valores de índice, cada uno de los cuales especifica una posición dentro de una dimensión de la `ICorDebugArrayValue` objeto.  
  
 Este valor no debe ser null.  
  
 `ppValue`  
 [out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor del elemento especificado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

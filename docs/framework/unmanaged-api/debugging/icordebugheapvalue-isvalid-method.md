---
title: ICorDebugHeapValue::IsValid (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ca3b86e90dcb76c1fece44cf2c5ed68e073d8e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757221"
---
# <a name="icordebugheapvalueisvalid-method"></a>ICorDebugHeapValue::IsValid (Método)
Obtiene un valor que indica si el objeto representado por ICorDebugHeapValue es válido.  
  
 Este método está desusado en .NET Framework versión 2.0.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbValid`  
 [out] Un puntero a un valor booleano que indica si este valor en el montón es válido.  
  
## <a name="remarks"></a>Comentarios  
 El valor no es válido si ha sido reclamado por el recolector de elementos no utilizados.  
  
 Este método está en desuso. En .NET Framework 2.0, todos los valores son válidos hasta [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) se denomina, en qué momento se invalidan los los valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

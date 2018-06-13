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
ms.openlocfilehash: 95532d6721467b482b1d79d611f8055b606bb4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413513"
---
# <a name="icordebugheapvalueisvalid-method"></a>ICorDebugHeapValue::IsValid (Método)
Obtiene un valor que indica si el objeto representado por este ICorDebugHeapValue es válido.  
  
 Este método está en desuso en la versión 2.0 de .NET Framework.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pbValid`  
 [out] Un puntero a un valor booleano que indica si este valor en el montón es válido.  
  
## <a name="remarks"></a>Comentarios  
 El valor no es válido si se ha recuperado por el recolector de elementos no utilizados.  
  
 Este método está en desuso. En la versión 2.0 de .NET Framework, todos los valores son válidos hasta [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) se llama, en cuyo momento se invalidan los los valores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

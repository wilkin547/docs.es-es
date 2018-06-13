---
title: ICorDebugCodeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 711c85b930617632d69497e4a9cf0a74360d27f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415112"
---
# <a name="icordebugcodeenumnext-method"></a>ICorDebugCodeEnum::Next (Método)
Obtiene el número especificado de instancias de "ICorDebugCode" de la enumeración, comenzando en la posición actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `celt`  
 [in] El número de `ICorDebugCode` instancias va a recuperar.  
  
 `values`  
 [out] Una matriz de punteros, cada uno de los cuales señala a un `ICorDebugCode` objeto.  
  
 `pceltFetched`  
 [out] Un puntero al número de `ICorDebugCode` instancias realmente devueltos. Este valor puede ser null si `celt` es uno.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
    
 

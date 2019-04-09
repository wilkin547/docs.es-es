---
title: ICorDebugCode::IsIL (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a82606d90444c2d543065287780e42da4f8b4943
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180692"
---
# <a name="icordebugcodeisil-method"></a>ICorDebugCode::IsIL (Método)
Obtiene un valor que indica si esta instancia de "ICorDebugCode" representa el código que se compila en lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbIL`  
 [out] `true` si este `ICorDebugCode` representa el código que se compila en MSIL; en caso contrario, `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

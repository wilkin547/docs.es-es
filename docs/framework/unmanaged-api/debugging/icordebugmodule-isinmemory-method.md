---
title: ICorDebugModule::IsInMemory (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: 637cac67e73d38aca0fdc5eaeae5405c4a859aa3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709822"
---
# <a name="icordebugmoduleisinmemory-method"></a>ICorDebugModule::IsInMemory (Método)

Obtiene un valor que indica si este módulo solo existe en la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pInMemory`  
 [out] `true` Si este módulo solo existe en la memoria; en caso contrario, `false` .  
  
## <a name="remarks"></a>Comentarios  

 El Common Language Runtime (CLR) admite la carga de módulos desde secuencias sin formato de bytes. Estos módulos se denominan *módulos en memoria* y no existen en el disco.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

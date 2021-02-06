---
description: 'Más información acerca de: ICorDebugModule:: Isinmemory ((método)'
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
ms.openlocfilehash: 41454ede15e1d45775af8fb0ab7a6b571d9c0e41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660094"
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
  
## <a name="remarks"></a>Observaciones  

 El Common Language Runtime (CLR) admite la carga de módulos desde secuencias sin formato de bytes. Estos módulos se denominan *módulos en memoria* y no existen en el disco.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

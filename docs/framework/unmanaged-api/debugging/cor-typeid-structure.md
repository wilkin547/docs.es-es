---
title: COR_TYPEID (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ca6c9b3b02314843a3eaf01d8cd4a9eac5513efa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cortypeid-structure"></a>COR_TYPEID (Estructura)
Contiene un identificador de tipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`token1`|El primer token.|  
|`token2`|El segundo token.|  
  
## <a name="remarks"></a>Comentarios  
 El `COR_TYPEID` estructura se devuelve un número de métodos de depuración que proporcionan información acerca de los objetos que se recolectarán como elementos no utilizados. A continuación, puede pasarse como argumento a otros métodos de depuración que proporcionan información adicional sobre dicho elemento. Por ejemplo, al enumerar un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto, puede recuperar individuales [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos que representan los objetos individuales en el montón administrado. A continuación, puede pasar el `COR_TYPEID` valor de la `COR_HEAPOBJECT.type` campo el [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) método para recuperar un objeto ICorDebugType que proporciona información de tipo sobre el objeto.  
  
 Un `COR_TYPEID` objeto está pensado para ser opaco. No se deben obtener acceso a o manipulan sus campos individuales. Su uso único es como un identificador que se proporciona como un `out` parámetro en una llamada al método y que puede, a su vez, se pasa a otros métodos para proporcionar información adicional.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

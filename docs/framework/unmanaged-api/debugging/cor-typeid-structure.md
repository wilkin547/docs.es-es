---
title: COR_TYPEID (Estructura)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51104516008ffee0694c72733cb5f82b5ba6d8cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109868"
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
 El `COR_TYPEID` estructura devuelto por una serie de métodos de depuración que proporcionan información acerca de los objetos para recopilar los elementos no utilizados. A continuación, puede pasarse como argumento a otros métodos de depuración que proporcionen información adicional sobre dicho elemento. Por ejemplo, al enumerar un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto, puede recuperar individuales [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos que representan objetos individuales en el montón administrado. A continuación, puede pasar el `COR_TYPEID` valor desde el `COR_HEAPOBJECT.type` campo el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) método para recuperar un objeto ICorDebugType que proporciona información sobre el objeto.  
  
 Un `COR_TYPEID` objeto está pensado para ser opaca. No se deben tener acceso a sus campos individuales ni manipular. Es su uso exclusivo como un identificador que se proporciona como un `out` parámetro en una llamada al método y que puede, a su vez, se pasa a otros métodos para proporcionar información adicional.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

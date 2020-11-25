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
ms.openlocfilehash: 5eeb5aef7edaa23385190a309144e1477da741e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697446"
---
# <a name="cor_typeid-structure"></a>COR_TYPEID (Estructura)

Contiene un identificador de tipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`token1`|El primer token.|  
|`token2`|Segundo token.|  
  
## <a name="remarks"></a>Comentarios  

 La `COR_TYPEID` estructura es devuelta por una serie de métodos de depuración que proporcionan información sobre los objetos que se van a recolectar como elemento no utilizado. A continuación, se puede pasar como argumento a otros métodos de depuración que proporcionan información adicional sobre ese elemento. Por ejemplo, al enumerar un objeto [icordebugheapenum (](icordebugheapenum-interface.md) , puede recuperar objetos individuales [COR_HEAPOBJECT](cor-heapobject-structure.md) que representan objetos individuales en el montón administrado. Después, puede pasar el `COR_TYPEID` valor del `COR_HEAPOBJECT.type` campo al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) para recuperar un objeto ICorDebugType que proporcione información de tipo sobre el objeto.  
  
 Un `COR_TYPEID` objeto está diseñado para ser opaco. No se debe tener acceso a sus campos individuales ni manipularlos. Su único uso es como un identificador que se proporciona como un `out` parámetro en una llamada al método y que, a su vez, se puede pasar a otros métodos para proporcionar información adicional.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

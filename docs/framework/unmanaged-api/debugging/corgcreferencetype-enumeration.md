---
title: CorGCReferenceType (enumeración)
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: 17d47b6242bb12ff5ca3cfbde3e4ec183b9c19fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793873"
---
# <a name="corgcreferencetype-enumeration"></a>CorGCReferenceType (enumeración)
Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>Miembros  
  
|Nombre de miembro|Descripción|  
|-----------------|-----------------|  
|`CorHandleStrong`|Identificador a una referencia segura de la tabla de identificadores de objetos.|  
|`CorHandleStrongPinning`|Identificador de una referencia segura anclada de la tabla de identificadores de objetos.|  
|`CorHandleWeakShort`|Identificador de una referencia débil de la tabla de identificadores de objetos.|  
|`CorHandleWeakRefCount`|Identificador de un objeto de cuenta de referencia débil de la tabla de identificadores de objetos.|  
|`CorHandleStrongRefCount`|Identificador de un objeto con recuento de referencias de la tabla de identificadores de objetos.|  
|`CorHandleStrongDependent`|Identificador de un objeto dependiente de la tabla de identificadores de objetos.|  
|`CorHandleStrongAsyncPinned`|Objeto anclado asincrónico de la tabla de identificadores de objetos.|  
|`CorHandleStrongSizedByref`|Identificador seguro que mantiene un tamaño aproximado del cierre colectivo de todos los objetos y raíces de objetos en tiempo de recolección de elementos no utilizados.|  
|`CorReferenceStack`|Referencia de la pila administrada.|  
|`CorReferenceFinalizer`|Referencia de la cola del finalizador.|  
|CorHandleStrongOnly|Devuelve solo las referencias fuertes de la tabla de identificadores. Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .|  
|`CorHandleWeakOnly`|Devuelve solo las referencias débiles de la tabla de identificadores. Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .|  
|`CorHandleAll`|Devuelve todas las referencias de la tabla de identificadores. Este valor solo lo usa el método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) .|  
  
## <a name="remarks"></a>Notas  
 La enumeración `CorGCReferenceType` se utiliza como sigue:  
  
- Como valor del campo `type` de la estructura [COR_GC_REFERENCE](cor-gc-reference-structure.md) , indica el origen de una referencia o un identificador.  
  
- Como `types` argumento al método [ICorDebugProcess5:: enumeratehandles (](icordebugprocess5-enumeratehandles-method.md) , especifica los tipos de identificadores que se van a incluir en la enumeración.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)

---
title: "CorGCReferenceType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a>CorGCReferenceType (Enumeración)
Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`CorHandleStrongPinning`|Un identificador de referencia segura anclada de la tabla de identificadores de objeto.|  
|`CorHandleWeakShort`|Un identificador para una referencia débil de la tabla de identificadores de objeto.|  
|`CorHandleWeakRefCount`|Un identificador para un objeto de recuento de referencia débil de la tabla de identificadores de objeto.|  
|`CorHandleStrongRefCount`|Un identificador a un objeto con recuento de referencias de la tabla de identificadores de objeto.|  
|`CorHandleStrongDependent`|Un identificador a un objeto dependiente de la tabla de identificadores de objeto.|  
|`CorHandleStrongAsyncPinned`|Objeto anclado asincrónico de la tabla de identificadores de objetos.|  
|`CorHandleStrongSizedByref`|Identificador seguro que mantiene un tamaño aproximado del cierre colectivo de todos los objetos y raíces de objetos en tiempo de recolección de elementos no utilizados.|  
|`CorReferenceStack`|Referencia de la pila administrada.|  
|`CorReferenceFinalizer`|Referencia de la cola del finalizador.|  
|CorHandleStrongOnly|Devolver solo referencias fuertes de la tabla de identificadores. Este valor se usa por la [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) método únicamente.|  
|`CorHandleWeakOnly`|Devolver solo referencias débiles de la tabla de identificadores. Este valor se usa por la [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) método únicamente.|  
|`CorHandleAll`|Devolver todas las referencias de la tabla de identificadores. Este valor se usa por la [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) método únicamente.|  
  
## <a name="remarks"></a>Comentarios  
 El `CorGCReferenceType` enumeración se utiliza como sigue:  
  
-   Como el valor de la `type` campo de la [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) estructura, indica que el origen de una referencia o un identificador.  
  
-   Como el `types` argumento pasado a la [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) método, especifica los tipos de controladores para incluir en la enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

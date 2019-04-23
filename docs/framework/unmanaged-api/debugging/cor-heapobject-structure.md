---
title: COR_HEAPOBJECT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f179b58ff8eb51e2843780d3212cf38ed7d13216
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168836"
---
# <a name="corheapobject-structure"></a>COR_HEAPOBJECT (Estructura)
Proporciona información sobre un objeto del montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`address`|La dirección del objeto en memoria.|  
|`size`|El tamaño total del objeto, en bytes.|  
|`type`|Un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token que representa el tipo del objeto.|  
  
## <a name="remarks"></a>Comentarios  
 `COR_HEAPOBJECT` las instancias se pueden recuperar mediante la enumeración de un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objeto de interfaz que se rellena mediante una llamada a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) método.  
  
 Un `COR_HEAPOBJECT` instancia proporciona información acerca de un objeto activo en el montón administrado, o sobre un objeto que no se ha modificado cualquier objeto, pero aún no se han recopilado por el recolector de elementos no utilizados.  
  
 Para mejorar el rendimiento, la `COR_HEAPOBJECT.address` campo es un `CORDB_ADDRESS` valor en lugar de ICorDebugValue valor usado en gran parte de la API de depuración de la interfaz. Para obtener un objeto ICorDebugValue para una dirección de un objeto determinado, puede pasar el `CORDB_ADDRESS` valor para el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) método.  
  
 Para mejorar el rendimiento, la `COR_HEAPOBJECT.type` campo es un `COR_TYPEID` valor usado en gran parte de la API de depuración de interfaz de valor en lugar de la instancia de ICorDebugType. Para obtener un objeto ICorDebugType para un identificador de un tipo determinado, puede pasar el `COR_TYPEID` valor para el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) método.  
  
 El `COR_HEAPOBJECT` estructura incluye una interfaz COM con recuento de referencias. Si recupera un `COR_HEAPOBJECT` instancia desde el enumerador mediante una llamada a la [Icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) método posteriormente debe liberar la referencia.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

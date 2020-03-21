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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179335"
---
# <a name="cor_heapobject-structure"></a>COR_HEAPOBJECT (Estructura)
Proporciona información sobre un objeto del montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`address`|La dirección del objeto en la memoria.|  
|`size`|El tamaño total del objeto, en bytes.|  
|`type`|Un [token de COR_TYPEID](cor-typeid-structure.md) que representa el tipo del objeto.|  
  
## <a name="remarks"></a>Observaciones  
 `COR_HEAPOBJECT`Instancias se pueden recuperar mediante la enumeración de un [ICorDebugHeapEnum](icordebugheapenum-interface.md) objeto de interfaz que se rellena mediante una llamada a la [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) método.  
  
 Una `COR_HEAPOBJECT` instancia proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está rooteado por ningún objeto pero que aún no ha sido recopilado por el recolector de elementos no utilizados.  
  
 Para un mejor `COR_HEAPOBJECT.address` rendimiento, `CORDB_ADDRESS` el campo es un valor en lugar del valor de la interfaz ICorDebugValue utilizado en gran parte de la API de depuración. Para obtener un ICorDebugValue objeto para una dirección `CORDB_ADDRESS` de objeto determinada, puede pasar el valor a la [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) método.  
  
 Para un mejor `COR_HEAPOBJECT.type` rendimiento, `COR_TYPEID` el campo es un valor en lugar del valor de la interfaz ICorDebugType utilizado en gran parte de la API de depuración. Para obtener un ICorDebugType objeto para un identificador `COR_TYPEID` de tipo determinado, puede pasar el valor a la [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) método.  
  
 La `COR_HEAPOBJECT` estructura incluye una interfaz COM con recuento de referencias. Si recupera `COR_HEAPOBJECT` una instancia del enumerador mediante una llamada a la [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) método, debe liberar posteriormente la referencia.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

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
ms.openlocfilehash: 270360a8950197eca14e02a60554659e5ac7b91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099076"
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`address`|Dirección del objeto en memoria.|  
|`size`|Tamaño total del objeto, en bytes.|  
|`type`|Un token de [COR_TYPEID](cor-typeid-structure.md) que representa el tipo del objeto.|  
  
## <a name="remarks"></a>Comentarios  
 `COR_HEAPOBJECT` instancias se pueden recuperar enumerando un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que se rellena llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .  
  
 Una instancia de `COR_HEAPOBJECT` proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.  
  
 Para mejorar el rendimiento, el campo `COR_HEAPOBJECT.address` es un valor `CORDB_ADDRESS` en lugar del valor de la interfaz ICorDebugValue usado en gran parte de la API de depuración. Para obtener un objeto ICorDebugValue para una dirección de objeto determinada, puede pasar el valor `CORDB_ADDRESS` al método [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 Para mejorar el rendimiento, el campo `COR_HEAPOBJECT.type` es un valor `COR_TYPEID` en lugar del valor de la interfaz ICorDebugType usado en gran parte de la API de depuración. Para obtener un objeto ICorDebugType para un identificador de tipo determinado, puede pasar el valor de `COR_TYPEID` al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) .  
  
 La estructura de `COR_HEAPOBJECT` incluye una interfaz COM con recuento de referencias. Si recupera una instancia de `COR_HEAPOBJECT` del enumerador mediante una llamada al método [icordebugheapenum (:: Next](icordebugheapenum-next-method.md) , debe liberar la referencia posteriormente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

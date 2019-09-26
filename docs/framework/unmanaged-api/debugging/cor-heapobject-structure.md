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
ms.openlocfilehash: c59ddec655f3127e8dab8d8c41543f03a896cf63
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274036"
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
 `COR_HEAPOBJECT`las instancias pueden recuperarse mediante la enumeración de un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que se rellena llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .  
  
 Una `COR_HEAPOBJECT` instancia de proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.  
  
 Para mejorar el rendimiento, `COR_HEAPOBJECT.address` el campo es `CORDB_ADDRESS` un valor en lugar del valor de la interfaz ICorDebugValue usado en gran parte de la API de depuración. Para obtener un objeto ICorDebugValue para una dirección de objeto determinada, puede pasar el `CORDB_ADDRESS` valor al método [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 Para mejorar el rendimiento, `COR_HEAPOBJECT.type` el campo es `COR_TYPEID` un valor en lugar del valor de la interfaz ICorDebugType usado en gran parte de la API de depuración. Para obtener un objeto ICorDebugType para un identificador de tipo determinado, puede pasar el `COR_TYPEID` valor al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) .  
  
 La `COR_HEAPOBJECT` estructura incluye una interfaz com con recuento de referencias. Si recupera una `COR_HEAPOBJECT` instancia del enumerador mediante una llamada al método [icordebugheapenum (:: Next](icordebugheapenum-next-method.md) , debe liberar posteriormente la referencia.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

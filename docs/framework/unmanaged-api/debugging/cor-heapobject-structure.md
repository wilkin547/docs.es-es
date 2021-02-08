---
description: 'Más información acerca de: estructura de COR_HEAPOBJECT'
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
ms.openlocfilehash: f41e02e7c528063f4b7ed485cbadbabb4d3e5ca7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801805"
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`address`|Dirección del objeto en memoria.|  
|`size`|Tamaño total del objeto, en bytes.|  
|`type`|[COR_TYPEID](cor-typeid-structure.md) token que representa el tipo del objeto.|  
  
## <a name="remarks"></a>Observaciones  

 `COR_HEAPOBJECT` las instancias pueden recuperarse mediante la enumeración de un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que se rellena llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .  
  
 Una `COR_HEAPOBJECT` instancia de proporciona información sobre un objeto activo en el montón administrado o sobre un objeto que no está raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.  
  
 Para mejorar el rendimiento, el `COR_HEAPOBJECT.address` campo es un `CORDB_ADDRESS` valor en lugar del valor de la interfaz ICorDebugValue usado en gran parte de la API de depuración. Para obtener un objeto ICorDebugValue para una dirección de objeto determinada, puede pasar el `CORDB_ADDRESS` valor al método [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 Para mejorar el rendimiento, el `COR_HEAPOBJECT.type` campo es un `COR_TYPEID` valor en lugar del valor de la interfaz ICorDebugType usado en gran parte de la API de depuración. Para obtener un objeto ICorDebugType para un identificador de tipo determinado, puede pasar el `COR_TYPEID` valor al método [ICorDebugProcess5:: gettypefortypeid (](icordebugprocess5-gettypefortypeid-method.md) .  
  
 La `COR_HEAPOBJECT` estructura incluye una interfaz com con recuento de referencias. Si recupera una `COR_HEAPOBJECT` instancia del enumerador mediante una llamada al método [icordebugheapenum (:: Next](icordebugheapenum-next-method.md) , debe liberar posteriormente la referencia.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

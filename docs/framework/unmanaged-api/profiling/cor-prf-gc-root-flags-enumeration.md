---
title: COR_PRF_GC_ROOT_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: bbc163c71b47e6fee0db89284d6e3fd27e882768
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500900"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS (Enumeración)
Indica una propiedad de una raíz de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|La raíz impide que una recolección de elementos no utilizados mueva el objeto.|  
|`COR_PRF_GC_ROOT_WEAKREF`|La raíz no impide la recolección de elementos no utilizados.|  
|`COR_PRF_GC_ROOT_INTERIOR`|La raíz hace referencia a un campo del objeto en lugar del propio objeto.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|La raíz evita la recolección de elementos no utilizados si el recuento de referencias del objeto es un determinado valor.|  
  
## <a name="remarks"></a>Comentarios  
 `COR_PRF_GC_ROOT_FLAGS`es una máscara de máscara que proporciona información adicional sobre raíces especiales. Sin embargo, no todas las raíces son especiales. Por ejemplo, algunas raíces no son referencias débiles, punteros interiores, ancladas o con recuento de referencias. Para tales raíces, no hay marcas para transmitir. Por lo tanto, los métodos que utilizan esta enumeración, como el método [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) , envían 0 para la máscara de máscara de marcas, lo que indica que todas las marcas están desactivadas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)

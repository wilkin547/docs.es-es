---
title: COR_ARRAY_LAYOUT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cccb862a0dfd16eb0bbfe557e3c35373cd7e7b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740811"
---
# <a name="corarraylayout-structure"></a>COR_ARRAY_LAYOUT (Estructura)
Proporciona información sobre la distribución de un objeto de matriz en la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`componentID`|El identificador del tipo de objetos que contiene la matriz.|  
|`componentType`|Un valor de enumeración CorElementType que indica si el componente es un tipo primitivo, una clase de valor o una referencia de la colección de elementos no utilizados.|  
|`firstElementOffset`|El desplazamiento al primer elemento de la matriz.|  
|`elementSize`|El tamaño de cada elemento.|  
|`countOffset`|El desplazamiento en el número de elementos de la matriz.|  
|`rankSize`|El tamaño de la clasificación, en bytes.|  
|`numRanks`|El número de rangos en la matriz.|  
|`rankOffset`|El desplazamiento en el que iniciar los rangos.|  
  
## <a name="remarks"></a>Comentarios  
 El `rankSize` campo especifica el tamaño de un rango en una matriz multidimensional. Es preciso para las matrices unidimensionales también.  
  
 El valor de `numRanks` es 1 para una matriz unidimensional y `N` para una matriz multidimensional de `N` dimensiones.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

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
ms.openlocfilehash: f37bf545553045b9737b7057feed78e1f06ace4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099466"
---
# <a name="cor_array_layout-structure"></a>COR_ARRAY_LAYOUT (Estructura)
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`componentID`|Identificador del tipo de objetos que contiene la matriz.|  
|`componentType`|Un valor de enumeración de CorElementType que indica si el componente es una referencia de recolección de elementos no utilizados, una clase de valor o un primitivo.|  
|`firstElementOffset`|Desplazamiento al primer elemento de la matriz.|  
|`elementSize`|Tamaño de cada elemento.|  
|`countOffset`|Desplazamiento al número de elementos de la matriz.|  
|`rankSize`|Tamaño del rango, en bytes.|  
|`numRanks`|Número de rangos de la matriz.|  
|`rankOffset`|Desplazamiento en el que se inician los rangos.|  
  
## <a name="remarks"></a>Comentarios  
 El campo `rankSize` especifica el tamaño de un rango en una matriz multidimensional. También es preciso para las matrices unidimensionales.  
  
 El valor de `numRanks` es 1 para una matriz unidimensional y `N` para una matriz multidimensional de dimensiones `N`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

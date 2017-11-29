---
title: COR_ARRAY_LAYOUT (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_ARRAY_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_ARRAY_LAYOUT
helpviewer_keywords: COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 02ddd87cfaf16990ff487dfe27f30a2493cb9a01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corarraylayout-structure"></a>COR_ARRAY_LAYOUT (Estructura)
Proporciona información sobre la distribución de un objeto de matriz en la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`componentID`|El identificador del tipo de objetos que contiene la matriz.|  
|`componentType`|Un valor de enumeración CorElementType que indica si el componente es una referencia de la colección de elementos no utilizados, una clase de valor o un tipo primitivo.|  
|`firstElementOffset`|El desplazamiento hasta el primer elemento de la matriz.|  
|`elementSize`|El tamaño de cada elemento.|  
|`countOffset`|El desplazamiento hasta el número de elementos de la matriz.|  
|`rankSize`|El tamaño de la clasificación, en bytes.|  
|`numRanks`|El número de rangos en la matriz.|  
|`rankOffset`|El desplazamiento en el que iniciar los rangos.|  
  
## <a name="remarks"></a>Comentarios  
 El `rankSize` campo especifica el tamaño de un rango en una matriz multidimensional. Es preciso para así matrices unidimensionales.  
  
 El valor de `numRanks` es 1 para una matriz unidimensional y `N` para una matriz multidimensional de `N` dimensiones.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)

---
title: COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: c92ee580caed9f1fb87a31b676747769ad31a0e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867261"
---
# <a name="cor_prf_function_argument_info-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)
Representa los argumentos de una función, ordenados de izquierda a derecha.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`numRanges`|El número de bloques de argumentos. Es decir, este valor es el número de estructuras [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) en la matriz de `ranges`.|  
|`totalArgumentSize`|Tamaño total de todos los argumentos. En otras palabras, este valor es la suma de las longitudes de los argumentos.|  
|`ranges`|Matriz de estructuras de `COR_PRF_FUNCTION_ARGUMENT_RANGE`, cada una de las cuales representa un bloque de argumentos de función.|  
  
## <a name="remarks"></a>Notas  
 Una función puede tener muchos argumentos. Es posible que esos argumentos no se almacenen de forma contigua en la memoria. Puede tener un bloque de tres argumentos en un lugar, un bloque de dos argumentos en otro lugar y un bloque final de un argumento en un lugar diferente. Estos argumentos son todos para la misma función; simplemente se almacenan en distintos lugares.  
  
 La estructura `COR_PRF_FUNCTION_ARGUMENT_INFO` representa todos los argumentos de una sola función. Utiliza una matriz para hacer referencia a todos los bloques de argumentos de función. Por lo tanto, para una sola función, tiene una única estructura de `COR_PRF_FUNCTION_ARGUMENT_INFO`, que hace referencia a varias estructuras `COR_PRF_FUNCTION_ARGUMENT_RANGE`, cada una de las cuales señala a uno o más argumentos de función.  
  
 Los argumentos que se almacenan en registros se desbordan en la memoria para compilar las estructuras.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras para generación de perfiles](profiling-structures.md)

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
ms.openlocfilehash: 2b01acbd617b13a64ef3dca6c8661f1e6bb067ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447384"
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
|`numRanges`|El número de bloques de argumentos. Es decir, este valor es el número de estructuras [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) en la matriz de `ranges`.|  
|`totalArgumentSize`|Tamaño total de todos los argumentos. En otras palabras, este valor es la suma de las longitudes de los argumentos.|  
|`ranges`|Matriz de estructuras de `COR_PRF_FUNCTION_ARGUMENT_RANGE`, cada una de las cuales representa un bloque de argumentos de función.|  
  
## <a name="remarks"></a>Comentarios  
 Una función puede tener muchos argumentos. Es posible que esos argumentos no se almacenen de forma contigua en la memoria. Puede tener un bloque de tres argumentos en un lugar, un bloque de dos argumentos en otro lugar y un bloque final de un argumento en un lugar diferente. Estos argumentos son todos para la misma función; simplemente se almacenan en distintos lugares.  
  
 La estructura `COR_PRF_FUNCTION_ARGUMENT_INFO` representa todos los argumentos de una sola función. Utiliza una matriz para hacer referencia a todos los bloques de argumentos de función. Por lo tanto, para una sola función, tiene una única estructura de `COR_PRF_FUNCTION_ARGUMENT_INFO`, que hace referencia a varias estructuras `COR_PRF_FUNCTION_ARGUMENT_RANGE`, cada una de las cuales señala a uno o más argumentos de función.  
  
 Los argumentos que se almacenan en registros se desbordan en la memoria para compilar las estructuras.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

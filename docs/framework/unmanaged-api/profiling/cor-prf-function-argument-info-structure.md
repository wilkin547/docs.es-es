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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 658b88349bedcbcefd0b97226c7bd1fa34f656c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781922"
---
# <a name="corprffunctionargumentinfo-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`numRanges`|El número de bloques de argumentos. Es decir, este valor es el número de [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) estructuras en el `ranges` matriz.|  
|`totalArgumentSize`|El tamaño total de todos los argumentos. En otras palabras, este valor es la suma de las longitudes de argumento.|  
|`ranges`|Una matriz de `COR_PRF_FUNCTION_ARGUMENT_RANGE` estructuras, cada uno de los cuales representa un bloque de argumentos de función.|  
  
## <a name="remarks"></a>Comentarios  
 Una función puede tener muchos argumentos. Estos argumentos no podrían almacenarse de forma contigua en la memoria. Podría tener un bloque de tres argumentos en un solo lugar, un bloque de dos argumentos en otro lugar y un bloque final de un argumento en un lugar diferente. Estos argumentos son todas de la misma función; simplemente se almacenan en distintos lugares.  
  
 El `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura representa todos los argumentos de una sola función. Usa una matriz para hacer referencia a todos los bloques de argumentos de función. Por lo tanto, para una sola función, tiene una sola `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura, que hace referencia a varios `COR_PRF_FUNCTION_ARGUMENT_RANGE` estructuras, cada uno de los cuales señala a uno o más argumentos de función.  
  
 Argumentos que se almacenan en los registros se vuelcan en la memoria para crear las estructuras.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

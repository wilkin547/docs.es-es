---
title: COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e26377fe3c5cfbae68f90087e3fb624ae4db0dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentinfo-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)
Representa los argumentos de una función, ordenados de izquierda a derecha.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`numRanges`|El número de bloques de argumentos. Es decir, este valor es el número de [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) las estructuras de los `ranges` matriz.|  
|`totalArgumentSize`|El tamaño total de todos los argumentos. En otras palabras, este valor es la suma de las longitudes de argumento.|  
|`ranges`|Una matriz de `COR_PRF_FUNCTION_ARGUMENT_RANGE` estructuras, cada uno de los cuales representa un bloque de argumentos de función.|  
  
## <a name="remarks"></a>Comentarios  
 Una función puede tener muchos argumentos. Los argumentos no podrían almacenarse de forma contigua en la memoria. Podría tener un bloque de tres argumentos en un solo lugar, un bloque de dos argumentos en otro lugar y un bloque final de un argumento en un lugar diferente. Estos argumentos son todos para la misma función; simplemente se almacenan en distintos lugares.  
  
 El `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura representa todos los argumentos de una función única. Utiliza una matriz para hacer referencia a todos los bloques de argumentos de función. Por lo tanto, para una única función, tiene un único `COR_PRF_FUNCTION_ARGUMENT_INFO` estructura, que hace referencia a varios `COR_PRF_FUNCTION_ARGUMENT_RANGE` estructuras, cada uno de los cuales señala a uno o más argumentos de función.  
  
 Argumentos que se almacenan en los registros se vuelcan en la memoria para compilar las estructuras.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

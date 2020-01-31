---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
ms.openlocfilehash: dae5ed7c25f85051d1a28681fb88b056617c4de0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867256"
---
# <a name="cor_prf_function_argument_range-structure"></a>COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)
Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembros|Descripción|  
|-------------|-----------------|  
|`startAddress`|Dirección inicial del bloque.|  
|`length`|Longitud del bloque contiguo.|  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras para generación de perfiles](profiling-structures.md)

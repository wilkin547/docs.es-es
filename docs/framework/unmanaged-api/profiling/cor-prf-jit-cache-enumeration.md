---
title: COR_PRF_JIT_CACHE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
ms.openlocfilehash: d19d7ed2262db6d3c6e7f15db0e96da52f86db4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500863"
---
# <a name="cor_prf_jit_cache-enumeration"></a>COR_PRF_JIT_CACHE (Enumeración)
Indica el resultado de una búsqueda de función en caché.  
  
> [!NOTE]
> `COR_PRF_CACHED_FUNCTION_FOUND`tiene un valor de cero, por lo que `COR_PRF_JIT_CACHE` no se puede usar como suplente booleano.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|La búsqueda encontró la función.|  
|`COR_PRF_FUNCTION_NOT_FOUND`|La búsqueda no encontró la función.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)

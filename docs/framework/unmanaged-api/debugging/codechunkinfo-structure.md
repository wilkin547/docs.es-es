---
title: Estructura CodeChunkInfo
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
ms.openlocfilehash: 11197246662a93f6a8b57c6e61e49505a9999d00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727437"
---
# <a name="codechunkinfo-structure"></a>Estructura CodeChunkInfo

Representa un único fragmento de código en la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`startAddr`|`CORDB_ADDRESS`Valor que especifica la dirección de inicio del fragmento.|  
|`length`|Tamaño, en bytes, del fragmento.|  
  
## <a name="remarks"></a>Comentarios  

 El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetCodeChunks](icordebugcode2-getcodechunks-method.md)
- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

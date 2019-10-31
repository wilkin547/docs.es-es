---
title: CodeChunkInfo (Estructura)
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
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132399"
---
# <a name="codechunkinfo-structure"></a>CodeChunkInfo (Estructura)

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
|`startAddr`|`CORDB_ADDRESS` valor que especifica la dirección inicial del fragmento.|  
|`length`|Tamaño, en bytes, del fragmento.|  
  
## <a name="remarks"></a>Comentarios  
 El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetCodeChunks (método)](icordebugcode2-getcodechunks-method.md)
- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36afee8af3de046683c55215a677a529b0837c77
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274254"
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
|`startAddr`|`CORDB_ADDRESS` Valor que especifica la dirección de inicio del fragmento.|  
|`length`|Tamaño, en bytes, del fragmento.|  
  
## <a name="remarks"></a>Comentarios  
 El único fragmento de código es una región de código nativo que forma parte de un objeto de código como una función.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetCodeChunks (método)](icordebugcode2-getcodechunks-method.md)
- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)

---
title: CLR_DEBUGGING_VERSION (Estructura)
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 651b916a0e3ca178432094428611f9bcc8f0fd17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132415"
---
# <a name="clr_debugging_version-structure"></a>CLR_DEBUGGING_VERSION (Estructura)
Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`wStructVersion`|El número de versión de la estructura|  
|`wMajor`|Número de versión principal.|  
|`wMinor`|Número de versión secundaria.|  
|`wBuild`|Número de compilación.|  
|`wRevision`|El número de revisión.|  
  
## <a name="remarks"></a>Comentarios  
 La estructura `CLR_DEBUGGING_VERSION` es igual que la estructura COR_VERSION, sin embargo, la estructura `CLR_DEBUGGING_VERSION` proporciona un campo de versión de estructura adicional (`wStructVersion`). Actualmente, este campo debe establecerse en cero.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
